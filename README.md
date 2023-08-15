#include <stdio.h>
#include <math.h>
//Sieve Eratosthenes
void sieve(int prime[], int n){
  //step 1: Assignment
  for(int i = 0; i < n; i++){
    prime[i] = 1; //Ban dau coi tat ca cac so deu la so nguyen to
  }
  //step 2: Sieve
  prime[0] = prime[1] = 0;
  for(int i = 2; i < sqrt(n); i++){
     //Neu i la so nguyen to, loai bo cac boi cua i
    if(prime[i] == 1){
      //Duyet cac boi cua i
      for(int j = i * i; j < n; j += i){
          prime[j] = 0;
      }
    }
  }
}
int main() {
  int n;
  scanf("%d", &n);
  int prime[n + 1];
  for(int i = 0; i <= n; i++){
    prime[i] = i;
  }
  sieve(prime, n);
  for(int i = 0; i <= n; i++){
    if(prime[i] == 1){
      printf("%d ", i);
    }
  }
  return 0;
}
