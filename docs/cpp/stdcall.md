---
title: __stdcall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __stdcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __stdcall keyword [C++]
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09efc905507d93bbb80b003f93b885d9d27fcb1d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939851"
---
# <a name="stdcall"></a>__stdcall
**Microsoft'a özgü**  
  
 **__Stdcall** çağırma kuralı Win32 API işlevleri çağırmak için kullanılır. Aranan, yığını temizler, derleyici yapsak **vararg** işlevleri **__cdecl**. Bu çağrı kuralını kullanan işlevler bir işlev prototipi gerektirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.  
  
|Öğe|Uygulama|  
|-------------|--------------------|  
|Bağımsız değişken geçirme sırası|Sağdan sola.|  
|Bağımsız değişken geçirme kuralı|Değer bir işaretçi veya başvuru türü geçirilmezse.|  
|Yığın bakımı sorumluluğu|Çağırılan işlev, yığından bağımsız kendi değişkenlerini yığından.|  
|Ad düzenleme kuralı|Bir alt çizgi (_) adın önekidir. Adın ardından at işareti (@) bağımsız değişken listesinde (ondalık) bayt sayısı ardından. Bu nedenle, bildirilen işlev `int func( int a, double b )` şu şekilde sunulur: `_func@12`|  
|Durum çevirisi kuralları|Yok.|  
  
 [/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneğini belirten **__stdcall** farklı bir çağırma kuralı açıkça bildirilmeyen tüm işlevler için.  
  
 Kullanılarak bildirilen işlevlerle **__stdcall** değiştirici dönüş değerleri kullanılarak bildirilen işlevlerle aynı şekilde [__cdecl](../cpp/cdecl.md).  
  
 ARM ve x64 işlemciler **__stdcall** kabul edilir ve derleyici tarafından; ARM ve x64 mimarileri, yoksayıldı. kural olarak, bağımsız değişkenler mümkün olduğunda kayıtlara geçirilir ve sonraki bağımsız değişkenler yığına geçirilir.  
  
 Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımı verildiğinde,  
  
```cpp  
struct CMyClass {  
   void __stdcall mymethod();  
};  
```  
  
 this  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 Şuna eşdeğerdir:  
  
```cpp  
void __stdcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte __ kullanın**stdcall** tüm sonuçları `WINAPI` işlevi standart arama olarak işlenen türleri:  
  
```cpp  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)