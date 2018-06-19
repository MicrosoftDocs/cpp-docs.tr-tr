---
title: __cdecl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __cdecl_cpp
dev_langs:
- C++
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d07c34c11037132b9f9695ec889bb681c7f43951
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414499"
---
# <a name="cdecl"></a>__cdecl
**Microsoft özel**  
  
 `__cdecl` Varsayılan C ve C++ programları için çağırma kuralı. Çağıran tarafından yığın Temizlenen çünkü bunu yapabilirsiniz **vararg** işlevleri. `__cdecl` Çağırma oluşturur daha büyük yürütülebilir dosyalar [__stdcall](../cpp/stdcall.md), çünkü yığın temizleme kodu dahil etmek için her işlev çağrısı gerektirir. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.  
  
|Öğe|Uygulama|  
|-------------|--------------------|  
|Bağımsız değişken geçirme sırası|Sağdan sola.|  
|Yığın bakımı sorumluluğu|Çağıran işlev, yığından bağımsız değişkenleri açar.|  
|Ad düzenleme kuralı|Alt çizgi karakteri (_) öneki ne zaman dışında adlarına \_C bağlantı kullanan _cdecl işlevler verilir.|  
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|  
  
> [!NOTE]
>  İlgili bilgi için bkz: [donatılmış adları](../build/reference/decorated-names.md).  
  
 Yer `__cdecl` bir değişken veya işlev adı önce değiştiricisi. Varsayılan adlandırma ve çağırma kuralları C olduğundan, yalnızca bir kez kullanmalısınız `__cdecl` x86 belirttiğiniz kod olduğunda **/GV** (vectorcall) **/Gz** (stdcall) veya  **/Gr** (fastcall) derleyici seçeneği. [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği zorlar `__cdecl` çağırma.  
  
 ARM ve x64 işlemciler `__cdecl` kabul ancak genellikle derleyici tarafından yoksayıldı. ARM ve x64 kuralına göre, bağımsız değişkenler mümkün olduğunda kayıtlarda geçirilir ve sonraki bağımsız değişkenler yığında geçirilir. X64 içindeki kod, kullanın `__cdecl` geçersiz kılmak için **/GV** derleyici seçeneği ve varsayılan x64 çağırma kullanın.  
  
 Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımını ele alalım:  
  
```cpp  
struct CMyClass {  
   void __cdecl mymethod();  
};  
```  
  
 bu:  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 şuna eşdeğerdir:  
  
```cpp  
void __cdecl CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, derleyici adlandırma ve çağırma kuralları için C kullanmak için talimat `system` işlevi.  
  
```cpp  
// Example of the __cdecl keyword on function  
int __cdecl system(const char *);  
// Example of the __cdecl keyword on function pointer  
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)