---
title: __fastcall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __fastcall_cpp
dev_langs: C++
helpviewer_keywords: __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ba2178c2dc06001476d8e9ff4b9aef239aa13fea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fastcall"></a>__fastcall
**Microsoft özel**  
  
 `__fastcall` Çağırma bağımsız değişkenlerinin işlevlere Yazmaçları, mümkün olduğunda geçirilecek olduğunu belirtir. Bu çağırma yalnızca x86 geçerlidir mimarisi. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.  
  
|Öğe|Uygulama|  
|-------------|--------------------|  
|Bağımsız değişken geçirme sırası|İlk iki DWORD veya bağımsız değişken listesinde soldan sağa bulunan küçük bağımsız değişkenleri ECX ve EDX yazmaçlar geçirilir; diğer tüm bağımsız değişkenler sağdan sola yığında geçirilir.|  
|Yığın bakımı sorumluluğu|İşlev POP yığından bağımsız değişkenleri olarak bilinir.|  
|Ad düzenleme kuralı|At işareti (@) adlarını; öneki bir at işareti parametresinde (ondalık) bayt sayısı ve ardından listesi adlarına sonekine.|  
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|  
  
> [!NOTE]
>  Gelecekteki derleyici sürümler farklı kasada parametreleri depolamak için kullanabilirsiniz.  
  
 Kullanarak [/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği olarak derlemek için modüldeki her işlevi neden `__fastcall` işlevi çakışan özniteliğini kullanarak bildirilmiş veya işlevin adını kaldırılana kadar `main`.  
  
 `__fastcall` Anahtar sözcüğünü kabul edilir ve hedef ARM ve x64 derleyicileri tarafından göz ardı mimarileri; x x64 yongası, kurala göre ilk dört bağımsız değişkenler yazmaçlar mümkün olduğunda geçirilir ve ek bağımsız değişkenler, yığında geçirilir. Daha fazla bilgi için bkz: [x64 genel bakış çağırma kuralları](../build/overview-of-x64-calling-conventions.md). ARM yonga üzerinde dört tamsayı kadar bağımsız değişkenleri ve sekiz kayan nokta değişkenleri Yazmaçları geçirilebilir ve ek bağımsız değişkenler yığında geçirilir.  
  
 Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir. Bu sınıf tanımını ele alalım:  
  
```cpp  
struct CMyClass {  
   void __fastcall mymethod();  
};  
```  
  
 bu:  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 şuna eşdeğerdir:  
  
```cpp  
void __fastcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, işlev `DeleteAggrWrapper` bağımsız değişkenleri Yazmaçları geçirilir:  
  
```cpp  
// Example of the __fastcall keyword  
#define FASTCALL    __fastcall  
  
void FASTCALL DeleteAggrWrapper(void* pWrapper);  
// Example of the __ fastcall keyword on function pointer  
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)