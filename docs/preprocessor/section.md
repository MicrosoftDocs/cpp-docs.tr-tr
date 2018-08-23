---
title: Bölüm | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- section_CPP
- vc-pragma.section
dev_langs:
- C++
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7601913b3940de8e6ade2c76100f4d773281db7
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464960"
---
# <a name="section"></a>section
Bir .obj dosyasında bölüm oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma section( "section-name" [, attributes] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Koşulları anlamını *segment* ve *bölümü* bu konudaki birbirinin yerine kullanılabilir.  
  
Bir bölüm tanımlandıktan sonra derleme geri kalanı için geçerli kalır. Ancak, kullanmalısınız [__declspec(allocate)](../cpp/allocate.md) veya hiçbir şey bölümünde yer alır.  
  
*Bölüm adı* bölümün adı gerekli bir parametredir. Adı herhangi bir standart bölüm adı ile çakışmaması gerekir. Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) kullanmamanız bölüm oluştururken adları listesi.  
  
*öznitelikleri* bölümüne atamak istediğiniz bir veya daha fazla virgülle ayrılmış özniteliklerin oluşan isteğe bağlı bir parametre. Olası *öznitelikleri* şunlardır:  
  
**read**  
Verileri okuma işlemleri sağlar.  
  
**write**  
Veri yazma işlemleri sağlar.  
  
**Yürütme**  
Yürütülecek kodu sağlar.  
  
**Paylaşılan**  
Resmi yüklemek tüm işlemler arasında bölümü paylaşır.  
  
**nopage**  
Bölüm alınabilir değil olarak işaretler; Win32 aygıt sürücülerini yönetmek için kullanışlıdır.  
  
**NoCache**  
Bölüm önbelleğe alınabilir değil olarak işaretler; Win32 aygıt sürücülerini yönetmek için kullanışlıdır.  
  
**Atma**  
Bölüm discardable olarak işaretler; Win32 aygıt sürücülerini yönetmek için kullanışlıdır.  
  
**remove**  
Bölüm değil bellekte olarak işaretler; Sanal cihaz sürücüleri (V*x*D) yalnızca.  
  
Öznitelikleri belirtmezseniz, bölümü okuyun ve yazma öznitelikleri.  
  
## <a name="example"></a>Örnek  
 
Aşağıdaki örnekte, ilk yönergesinin bölümü ve özniteliklerini tanımlar. Tamsayı `j` içine yerleştirin değil `mysec` ile bildirilmedi çünkü `__declspec(allocate)`; `j` veri bölüme gider. Tamsayı `i` kısımlarda `mysec` sonucu olarak, `__declspec(allocate)` depolama sınıfı özniteliği.  
  
```cpp  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)