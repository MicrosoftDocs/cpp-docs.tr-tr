---
---
# <a name="compiler-warning-level-1-c4055"></a>Derleyici Uyarısı (düzey 1) C4055  
  
'dönüştürme': veri işaretçi 'type1' işlev işaretçisi 'type2' den  
  
**Artık kullanılmıyor:** bu uyarı, Visual Studio 2017 ve sonraki sürümler tarafından oluşturulmaz.

 Bir veri işaretçisi (büyük olasılıkla yanlış) bir işlev işaretçisi dönüştürün. Düzey 1 uyarısı /Za altında ve düzey 4 uyarı /Ze altında budur.  
  
 Aşağıdaki örnek C4055 oluşturur:  
  
```C  
// C4055.c  
// compile with: /Za /W1 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
   return (PFUNC)pi;   // C4055  
}  
```  
  
 /Ze altında bir düzey 4 uyarı budur.  
  
```C  
// C4055b.c  
// compile with: /W4 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
return (PFUNC)pi;   // C4055  
}  
```