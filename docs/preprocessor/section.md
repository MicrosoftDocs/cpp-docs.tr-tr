---
title: "Bölüm | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10f5783c6712852bfb53f457cea174f699c01ea0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
  
 `attributes` bölümüne atamak istediğiniz bir veya daha fazla virgülle ayrılmış özniteliklerin oluşan isteğe bağlı bir parametre. Olası `attributes` şunlardır:  
  
 **read**  
 Verileri okuma işlemlerine izin verir.  
  
 **write**  
 Veri yazma işlemlerine izin verir.  
  
 **execute**  
 Yürütülen kod sağlar.  
  
 **Paylaşılan**  
 Görüntü yükleme tüm işlemler arasında bölüm paylaşır.  
  
 **nopage**  
 Bölüm disk belleğine alınabilir değil olarak işaretler; Win32 aygıt sürücüleri için kullanışlıdır.  
  
 **nocache**  
 Bölüm değil alınabilir olarak işaretler; Win32 aygıt sürücüleri için kullanışlıdır.  
  
 **atma**  
 Bölüm discardable olarak işaretler; Win32 aygıt sürücüleri için kullanışlıdır.  
  
 **remove**  
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
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)