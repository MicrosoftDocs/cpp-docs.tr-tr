---
title: Özel üye işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 12/06/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- special member functions [C++]
- constructors [C++]
- destructors [C++]
- copy operators [C++]
- move operators [C++]
- assignment operators [C++]
ms.assetid: 017d6817-b012-44f0-b153-f3076c251ea7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76be131193508e4def79c6e178e27cd671c7ce11
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="special-member-functions"></a>Özel üye işlevleri  
  
*Özel üye işlevleri* sınıfı (veya yapı) belirli durumlarda, derleyici otomatik olarak sizin için oluşturur, üye işlevlerdir. Bu işlevler [varsayılan oluşturucu](constructors-cpp.md#default_constructors), [yıkıcı](destructors-cpp.md), [kopya oluşturucu ve kopya atama işleci](copy-constructors-and-copy-assignment-operators-cpp.md)ve [taşıma oluşturucusu ve taşıma atama işlecine](move-constructors-and-move-assignment-operators-cpp.md). Sınıfınızda bir veya daha fazla özel üye işlevleri tanımlamıyorsa, ardından derleyici örtük olarak bildirme ve kullanılan işlevleri tanımlayın. Derleyicinin ürettiği uygulamaları adlı *varsayılan* özel üye işlevleri. Gerekli olmadığında, derleyici işlevleri oluşturmaz.  
  
Varsayılan özel üye işlevi kullanarak açıkça bildirebilirsiniz `= default` anahtar sözcüğü. Bu işlev hiç bildirilmedi gibi yalnızca aynı şekilde gerekirse işlevi tanımlamak derleyici neden olur. 

Bazı durumlarda, derleyici verebilir *silinmiş* tanımlı ve bu nedenle değil aranabilir olmayan özel üye işlevleri. Bu, burada bir sınıftaki belirli özel üye işlevine bir çağrı sınıfının diğer özelliklerini verilen, anlamsız durumlarda gerçekleşebilir. Açıkça özel üye işlevi otomatik olarak oluşturulmasını önlemek için bunu kullanarak silinmiş olarak bildirebilirsiniz `= delete` anahtar sözcüğü.  
  
Derleyici oluşturan bir *varsayılan oluşturucu*, yalnızca başka bir kurucu bildirmemiş yükleyen, bağımsız değişken almayan bir oluşturucu. Parametreler isteyen bir oluşturucu bildirilen, varsayılan bir oluşturucu çağrısı girişiminde kodu bir hata iletisi oluşturmak üzere derleyici neden olur. Derleyicinin ürettiği varsayılan oluşturucu member-wise basit gerçekleştirir [başlatma varsayılan](initializers.md#default_initialization) nesnesinin. Varsayılan olarak başlatılması, tüm üye değişkenleri belirsiz bir durumda bırakır.  
  
Varsayılan yıkıcı nesnesinin member-wise yok etme gerçekleştirir. Yalnızca bir temel sınıf yıkıcı sanal ise sanal olur.  
  
Varsayılan kopyalama ve taşıma yapım ve atama işlemleri member-wise bit desenini gerçekleştirmek kopyalar veya statik olmayan veri üyeleri taşır. Hiçbir yıkıcı veya taşıma veya kopyalama işlemleri bildirirken işlemleri yalnızca oluşturulan taşıyın. Kopya Oluşturucu bildirilmişse varsayılan kopya Oluşturucu yalnızca oluşturulur. Bir taşıma işlemi bildirilirse örtük olarak silinir. Yalnızca hiçbir kopya atama işleci açıkça bildirilmişse varsayılan kopya atama işleci oluşturulur. Bir taşıma işlemi bildirilirse örtük olarak silinir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C++ Dil Başvurusu](cpp-language-reference.md)  



 
