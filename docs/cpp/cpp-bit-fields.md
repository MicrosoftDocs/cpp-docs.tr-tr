---
title: "C++ Bit alanları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 01a346054fff0f8f3a9a1407c17e28e8dc234a57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-bit-fields"></a>C++ Bit Alanları
Sınıflar ve yapılar, tamsayı türünden daha az depolama alanı kaplayan üyeler içerebilir. Bu üyeler bit alanları olarak belirtilir. Bit alanı sözdizimi *üye bildirimcisi* belirtimi aşağıdadır:  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
declarator  : constant-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 (İsteğe bağlı) `declarator` programda erişilen üyenin adıdır. Bu (numaralandırılmış türler dahil) bir tamsayı türü olmalıdır. *Sabit ifadesi* yapısında üye kapladığı bit sayısını belirtir. Doldurmak için, adsız bit alanları (diğer bir deyişle, hiçbir tanımlayıcısı olmayan bit alanları) kullanılabilir.  
  
> [!NOTE]
>  0 genişlikteki adlandırılmamış bir bit alanı, sıradaki bit alanını bir sonraki `type` sınırına hizalanmaya zorlar, burada `type` üyenin türüdür.  
  
 Aşağıdaki örnek bit alanlarını içeren bir yapıyı bildirir:  
  
```  
// bit_fields1.cpp  
// compile with: /LD  
struct Date {  
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned short nMonth    : 5;    // 0..12  (5 bits)  
   unsigned short nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 `Date` türünde bir nesnenin kavramsal bellek düzeni aşağıdaki çizimde gösterilmiştir.  
  
 ![Tarih nesnesi bellek düzenini](../cpp/media/vc38uq1.png "vc38UQ1")  
Tarih Nesnesinin Bellek Düzeni  
  
 Unutmayın `nYear` 8 bit uzunluğunda olduğunu ve word sınır bildirilen türünde taşma oluşturursunuz **kısa imzasız**. Bu nedenle, yeni bir başında başlamış **kısa imzasız**. Tüm bit alanlarının temel türün bir nesnesine sığmasına gerek yoktur; yeni depolama birimleri bildirimde istenen bit sayısına göre ayrılır.  
  
 **Microsoft özel**  
  
 Yukarıdaki şekilde gösterildiği gibi, bildirilen verilerin bit alanları olarak sıralanması düşük bitten yüksek bite doğrudur.  
  
 **SON Microsoft özel**  
  
 Böyle bir yapının bildirimi, aşağıdaki örnekte gösterildiği gibi uzunluğu 0 olan adlandırılmamış bir alanı içeriyorsa,  
  
```  
// bit_fields2.cpp  
// compile with: /LD  
struct Date {  
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned           : 0;    // Force alignment to next boundary.  
   unsigned nMonth    : 5;    // 0..12  (5 bits)  
   unsigned nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 bellek düzeni aşağıdaki şekilde gösterildiği gibidir.  
  
 ![Tarih nesnesi sıfır &#45;yerleşimini; uzunluğunu bit alan](../cpp/media/vc38uq2.png "vc38UQ2")  
Sıfır Uzunluklu Bit Alanı Olan Tarih Nesnesinin Düzeni  
  
 Temel alınan bir bit alanı bir tamsayı türü açıklandığı gibi türünde olmalıdır [temel türleri](../cpp/fundamental-types-cpp.md).  
  
## <a name="restrictions-on-bit-fields"></a>Bit alanları kısıtlamaları  
 Bit alanlarındaki hatalı işlemler aşağıdaki listede görülmektedir:  
  
1.  Bir bit alanı adresini alma.  
  
2.  Bir başvuruyu bit alanı ile başlatma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve yapılar](../cpp/classes-and-structs-cpp.md)