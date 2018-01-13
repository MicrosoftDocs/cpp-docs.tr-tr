---
title: Hizalama (C++ bildirimleri) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 019884793eb3472e52c7772351b2f5826520a193
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alignment-c-declarations"></a>Hizalama (C++ Bildirimleri)
C++ alt düzey özelliklerini de belirli donanım mimarisi en büyük avantajlarından yararlanmak bellekte nesneleri kesin hizalamasını belirtin yeteneğidir. Varsayılan olarak, kendi boyutu değeri sınıfı ve yapı üyelerinde derleyici hizalar: bool ve char hizalanır tek tek baytlık sınırları, iki bayt üzerinde kısa, dört bayt uzun uzun Int çift ve uzun çift sekiz bayt. Çoğu senaryoda asla varsayılan hizalamayı zaten en iyi olduğundan hizalama ile ilgilenen olmanız gerekir. Bazı durumlarda ancak, önemli ölçüde performans artışı veya bellek tasarruf veri yapıları için özel bir hizalama belirterek elde edebilirsiniz. Visual Studio 2015 öncesinde varsayılandan daha büyük bir hizalama belirtmek için Microsoft'a özgü anahtar sözcükler __alignof ve declspec(alignas) kullanabilirsiniz. Visual Studio 2015'te, başlangıç C ++ 11 standart anahtar sözcükleri kullanması gereken [alignof ve alignas](../cpp/alignof-and-alignas-cpp.md) en fazla kod taşınabilirlik için. Yeni anahtar sözcüklerin Microsoft'a özgü uzantılar başlık altında aynı şekilde davranır ve bu uzantılar belgelerine yeni anahtar sözcüklerin için de geçerlidir. Bkz: [__alignof işleci](../cpp/alignof-operator.md) ve [Hizala](../cpp/align-cpp.md) daha fazla bilgi için. C++ Standart yine de Microsoft #pragma kullanmanız gerekiyorsa hedef platformu için derleyici varsayılan değerinden küçük sınırlarındaki hizalama için paketleme davranışı belirtmiyor [paketi](../preprocessor/pack.md) bu durumda.  
  
 C++ Standart Kitaplığı sağlar [aligned_storage sınıfı](../standard-library/aligned-storage-class.md) Özel hizalamaları ile veri yapıları için bellek tahsis etmek için ve [aligned_union sınıfı](../standard-library/aligned-union-class.md) ile birleşimler hizalamasını belirtmek için Önemsiz olmayan oluşturucular veya Yıkıcılar.  
  
## <a name="about-alignment"></a>Hizalama hakkında  
 Hizalama 2'in modulo sayısal adresi olarak ifade edilen bir bellek adresi özelliğidir. Örneğin, 0x0001103F 4 modül 3 adresidir; Bu adres hizalanacak 4n + 3, 4 2'in seçilen üssü burada gösterir kabul edilir. Bir adresi hizalamasını iki seçilen gücüyle bağlıdır. Modül 8 7 adrestir. Bir adresi kendi hizalama Xn + 0 ise X hizalanacak kabul edilir.  
  
 CPU yönergeleri yürütmek bellekte depolanan veriler üzerinde çalışır ve veri adreslerini bellekte tarafından tanımlanır. Adresini yanı sıra tek bir datum ayrıca bir boyutu vardır. Adresini aksi boyutuna ve yanlış hizalanmış hizalanır gerekiyorsa bir datum doğal hizalanmış denir. Örneğin, tanımlamak için kullanılan adres için 8 hizalanır, 8-bayt kayan nokta datum doğal olarak hizalanır.  
  
 Veri alignmentDevice derleyicileri derleyici işlenmesini verileri veri uyuşmazlığın engelleyen bir şekilde tahsis dener.  
  
 Basit veri türleri için veri türünde bayt boyutu'nün katları adreslerinin derleyici atar. Bu nedenle, derleyici uzun türündeki dört, ayarlama adresinin alt iki biti sıfıra katları olan değişkenler adresleri atar.  
  
 Ayrıca, derleyicinin doğal olarak her öğe yapısı uyacak şekilde yapılarda klavye takımı. Aşağıdaki kod örneğinde yapısı yapısı x_ göz önünde bulundurun:  
  
```  
struct x_  
{  
   char a;     // 1 byte  
   int b;      // 4 bytes  
   short c;    // 2 bytes  
   char d;     // 1 byte  
} MyStruct;  
  
```  
  
 Derleyici hizalama doğal zorlamak için bu yapı pads.  
  
 Aşağıdaki kod örneğinde nasıl derleyici doldurulan yapısı bellek: kopyalama yerleştirir gösterir  
  
```  
// Shows the actual memory layout  
struct x_  
{  
   char a;            // 1 byte  
   char _pad0[3];     // padding to put 'b' on 4-byte boundary  
   int b;            // 4 bytes  
   short c;          // 2 bytes  
   char d;           // 1 byte  
   char _pad1[1];    // padding to make sizeof(x_) multiple of 4  
}  
  
```  
  
1.  Her iki bildirimleri sizeof(struct x_) 12 bayt döndürür.  
  
2.  İkinci bildirim iki doldurma öğeleri içerir:  
  
3.  _pad0 char dört baytlık sınır int b üyesinde hizalamak için [3]  
  
4.  _pad1 char [3]; çubuğu yapısı yapısı _x dizi öğelerini hizalamak için [1]  
  
5.  Doldurma öğelerini çubuğu [3] doğal erişimine izin veren şekilde hizalar.  
  
 Aşağıdaki kod örneğinde çubuğu gösterir [3] dizi düzeni:  
  
```  
adr offset   element  
------   -------  
0x0000   char a;         // bar[0]  
0x0001   char pad0[3];  
0x0004   int b;  
0x0008   short c;  
0x000a   char d;  
0x000b   char _pad1[1];  
  
0x000c   char a;         // bar[1]  
0x000d   char _pad0[3];  
0x0010   int b;  
0x0014   short c;  
0x0016   char d;  
0x0017   char _pad1[1];  
  
0x0018   char a;         // bar[2]  
0x0019   char _pad0[3];  
0x001c   int b;  
0x0020   short c;  
0x0022   char d;  
0x0023   char _pad1[1];  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri yapı hizalama](http://en.wikipedia.org/wiki/Data_structure_alignment)