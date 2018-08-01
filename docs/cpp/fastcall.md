---
title: __fastcall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fastcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e32bb8ac2fa453159b501ddc848348952b8d4468
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401736"
---
# <a name="fastcall"></a>__fastcall
**Microsoft'a özgü**  
  
 **__Fastcall** çağırma kuralı işlevlere bağımsız değişkenler, mümkün olduğunda kayıtlara geçirilebilir olduğunu belirtir. Bu çağırma kuralı yalnızca x86 için geçerlidir mimarisi. Aşağıdaki liste bu çağırma kuralının uygulamasını gösterir.  
  
|Öğe|Uygulama|  
|-------------|--------------------|  
|Bağımsız değişken geçirme sırası|İlk iki DWORD veya bağımsız değişken listesinde soldan sağa bulunan daha küçük bağımsız değişken ECX ve EDX kayıtlara geçirilir; Tüm diğer bağımsız değişkenler yığında sağdan sola geçirilir.|  
|Yığın bakımı sorumluluğu|Çağırılan işlev, yığından bağımsız değişkenleri yığından.|  
|Ad düzenleme kuralı|At işareti (\@); adların bir at işareti parametresinde (ondalık) bayt sayısı ardından liste adların.|  
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|  
  
> [!NOTE]
>  Gelecekteki derleyici sürümleri, parametreleri depolamak için farklı yazmaçlar kullanabilir.  
  
 Kullanarak [GR](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği olarak derlemek için modüldeki her işlevin neden **__fastcall** çakışan bir öznitelik kullanarak bildirilen işlev veya işlevin adı sürece `main` .  
  
 **__Fastcall** anahtar sözcüğünü kabul edilir ve ARM ve x64 hedefleyen derleyicileri tarafından göz ardı mimarileri; x x64 yonga, kural olarak, ilk dört bağımsız değişkenler mümkün olduğunda kayıtlara geçirilir ve ek bağımsız değişkenler geçirilir Yığında. Daha fazla bilgi için [x64 bakış çağırma kuralları](../build/overview-of-x64-calling-conventions.md). ARM bir yonga üzerinde en çok dört tamsayı bağımsız değişken ve sekiz kayan nokta değişkeni kayıtlara geçirilebilir ve ek bağımsız değişkenler yığına geçirilir.  
  
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
 Aşağıdaki örnekte, işlev `DeleteAggrWrapper` kayıtlara geçirilen bağımsız değişkenler:  
  
```cpp  
// Example of the __fastcall keyword  
#define FASTCALL    __fastcall  
  
void FASTCALL DeleteAggrWrapper(void* pWrapper);  
// Example of the __ fastcall keyword on function pointer  
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)