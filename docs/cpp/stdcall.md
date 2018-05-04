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
ms.openlocfilehash: f018a87f7a73de6500294b0817263e6f847af8ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="stdcall"></a>__stdcall
**Microsoft özel**  
  
 `__stdcall` Çağırma Win32 API işlevleri çağırmak için kullanılır. Derleyici yapar şekilde aranan yığını temizler **vararg** işlevler `__cdecl`. Bu arama kuralı kullanmak işlevleri işlev prototipi gerektirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.  
  
|Öğe|Uygulama|  
|-------------|--------------------|  
|Bağımsız değişken geçirme sırası|Sağdan sola.|  
|Bağımsız değişken geçirme kuralı|Değer bir işaretçi veya reference türü geçirilen sürece.|  
|Yığın bakımı sorumluluğu|İşlev POP yığından kendi bağımsız değişkenleri olarak bilinir.|  
|Ad düzenleme kuralı|Bir alt çizgi (_) adına önek. Tarafından adından at işareti (@) bağımsız değişken listesinde (ondalık) bayt sayısı ve ardından. Bu nedenle, olarak bildirilen bir işlev `int func( int a, double b )` gibi donatılmış: `_func@12`|  
|Durum çevirisi kuralları|Yok.|  
  
 [/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği belirtir `__stdcall` açıkça farklı bir arama kuralı ile bildirilen tüm işlevler için.  
  
 İşlevler kullanılarak bildirilen `__stdcall` değiştiricisi dönüş değerleri kullanılarak bildirilen işlevler aynı şekilde [__cdecl](../cpp/cdecl.md).  
  
 ARM ve x64 işlemciler `__stdcall` kabul edilir ve ARM ve x64; derleyici tarafından mimarileri göz ardı kurala göre bağımsız değişken yazmaçlar mümkün olduğunda geçirilir ve sonraki bağımsız değişkenler, yığında geçirilir.  
  
 Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımını verildiğinde,  
  
```cpp  
struct CMyClass {  
   void __stdcall mymethod();  
};  
```  
  
 this  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 Bunun için eşdeğerdir  
  
```cpp  
void __stdcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, kullanma __**stdcall** tüm sonuçları `WINAPI` işlevi türleri standart araması olarak işlenen:  
  
```cpp  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)