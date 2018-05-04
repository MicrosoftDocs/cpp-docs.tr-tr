---
title: C Bit alanları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitfields
- bit fields
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af47bbebdf3b3a71e2b63b07a1fa467801728061
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-bit-fields"></a>C Bit Alanları
Bir yapı veya birleşim üyeleri için Bildirimciler yanı sıra yapısı bildirimcisi de bir belirtilen bit sayısı kadar bir "bit alanı." olarak adlandırılan, olabilir Uzunluğu alan adı bildirimcisi gelen iki nokta ile ayarlanır devre dışı. Bir bit alanı bir tamsayı türü olarak yorumlanır.  
  
## <a name="syntax"></a>Sözdizimi  
 *Yapı bildirimcisi*:  
 *bildirimcisi*  
  
 *tür belirteci bildirimcisi* kabul **:** *sabit ifadesi*  
  
 *Sabit ifadesi* alan genişliğini bit cinsinden belirtir. *Tür belirteci* için `declarator` olmalıdır `unsigned int`, **imzalı int**, veya `int`ve *sabit ifadesi* negatif olmayan bir olmalıdır tamsayı değeri. Değer sıfırsa bildirimi sahip olmayan `declarator`. Bit alanları dizileri, bit alanları ve bit alanları dönmeden işlev işaretçileri izin verilmez. İsteğe bağlı `declarator` bit alan adları. Bit alanları yalnızca bir yapısının bir parçası bildirilebilir. Address-of işleci (**&**) bit alanı bileşenlerine uygulanamaz.  
  
 Adlandırılmamış bit alanları başvurulamaz ve içerikleri çalışma zamanında öngörülemeyen sonuçlara yol açabilir. Bunlar "kukla" alanlar olarak hizalama amacıyla kullanılabilir. Genişlik 0 içinde aşağıdaki üyesi için o depolama garanti olarak belirtilen bir adlandırılmamış bit alanı *yapısı bildirimi listesi* üzerinde başlayan bir `int` sınır.  
  
 Bit alanları ayrıca bit desenini içerecek şekilde yeterince uzun olmalıdır. Örneğin, bu iki ifade geçerli değil:  
  
```  
short a:17;        /* Illegal! */  
int long y:33;     /* Illegal! */  
```  
  
 Bu örnek iki boyutlu bir dizi adlı yapıların tanımlar `screen`.  
  
```  
struct   
{  
    unsigned short icon : 8;  
    unsigned short color : 4;  
    unsigned short underline : 1;  
    unsigned short blink : 1;  
} screen[25][80];  
```  
  
 Dizi 2.000 öğeleri içerir. Her öğe dört bit alanı üyelerini içeren bir tek tek yapısıdır: `icon`, `color`, `underline`, ve `blink`. Her yapısı iki bayt boyutudur.  
  
 Bit alanları tamsayı türü olarak aynı semantiklerine sahip. Başka bir deyişle, kaç tane BITS bit alanında yer alan bağımsız olarak aynı temel türünde bir değişken kullanılacak olarak bir bit alan ifadelerinde tam olarak aynı şekilde kullanılır.  
  
 **Microsoft özel**  
  
 Bit alanları olarak tanımlanan `int` imzalanmış olarak kabul edilir. Bir Microsoft uzantısı için ANSI C Standart sağlar `char` ve **uzun** türleri (her ikisi de **imzalı** ve `unsigned`) bit alanları için. Bit alanları temel türü ile adlandırılmamış **uzun**, **kısa**, veya `char` (**imzalı** veya `unsigned`) bir sınır hizalama temel türü için uygun zorla.  
  
 Bit alanları, bir tamsayı içinde en az önemli olan bitten en önemli bite doğru ayrılır. Aşağıdaki kodda  
  
```  
struct mybitfields  
{  
    unsigned short a : 4;  
    unsigned short b : 5;  
    unsigned short c : 7;  
} test;  
  
int main( void );  
{  
    test.a = 2;  
    test.b = 31;  
    test.c = 0;  
}  
```  
  
 bitler aşağıdaki gibi düzenlenir:  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 Tamsayı değerleri tamsayı yüksek bayt önce düşük baytını işlemciler 8086 ailesi depolar bu yana `0x01F2` yukarıdaki fiziksel bellekte depolanır `0xF2` arkasından `0x01`.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapı Bildirimleri](../c-language/structure-declarations.md)