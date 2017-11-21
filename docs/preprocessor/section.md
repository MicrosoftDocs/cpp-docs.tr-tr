---
title: "Bölüm | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- section_CPP
- vc-pragma.section
dev_langs: C++
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bdf0a02155329de5b77ffa67a8bc77ab34cc3e07
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="section"></a>section
Bir bölümün bir .obj dosyasında oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Koşulları anlamını *segment* ve *bölüm* bu konudaki birbirinin yerine kullanılabilir.  
  
 Bir bölüm tanımlandıktan sonra derleme geri kalanı için geçerli kalır. Ancak, kullanmalıdır [__declspec(allocate)](../cpp/allocate.md) veya hiçbir şey bölümünde yer alır.  
  
 *Bölüm adı* bölümünün adı gerekli bir parametredir. Adı herhangi bir standart bölüm adları ile çakışmaması gerekir. Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) değil kullanmanız gereken bir bölüm oluştururken adları listesi.  
  
 `attributes`bölümüne atamak istediğiniz bir veya daha fazla virgülle ayrılmış özniteliklerin oluşan isteğe bağlı bir parametre. Olası `attributes` şunlardır:  
  
 **Okuma**  
 Verileri okuma işlemlerine izin verir.  
  
 **yazma**  
 Veri yazma işlemlerine izin verir.  
  
 **Yürütme**  
 Yürütülen kod sağlar.  
  
 **Paylaşılan**  
 Görüntü yükleme tüm işlemler arasında bölüm paylaşır.  
  
 **nopage**  
 Bölüm disk belleğine alınabilir değil olarak işaretler; Win32 aygıt sürücüleri için kullanışlıdır.  
  
 **NoCache**  
 Bölüm değil alınabilir olarak işaretler; Win32 aygıt sürücüleri için kullanışlıdır.  
  
 **atma**  
 Bölüm discardable olarak işaretler; Win32 aygıt sürücüleri için kullanışlıdır.  
  
 **Kaldır**  
 Bölüm değil bellekte olarak işaretler; Sanal cihaz sürücüleri (V*x*D) yalnızca.  
  
 Öznitelikler belirtmezseniz, bölümünü okuyun ve yazma öznitelikleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, ilk yönerge bölümü ve öznitelikleri tanımlar. Tamsayı `j` içine koyun değil `mysec` ile bildirilmedi çünkü `__declspec(allocate)`; `j` veri bölüme gider. Tamsayı `i` yerleştirilmesini `mysec` sonucu olarak kendi `__declspec(allocate)` depolama sınıfı öznitelik.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)