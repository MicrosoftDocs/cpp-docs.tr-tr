---
description: 'Daha fazla bilgi edinin: özel üye işlevleri'
title: Özel üye işlevleri
ms.date: 12/06/2016
helpviewer_keywords:
- special member functions [C++]
- constructors [C++]
- destructors [C++]
- copy operators [C++]
- move operators [C++]
- assignment operators [C++]
ms.assetid: 017d6817-b012-44f0-b153-f3076c251ea7
ms.openlocfilehash: ab3b5be3c7006729e135cc273e9b7856adbd3252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113837"
---
# <a name="special-member-functions"></a>Özel üye işlevleri

*Özel üye işlevleri* , bazı durumlarda derleyicinin sizin için otomatik olarak oluşturduğu Sınıf (veya yapı) üye işlevleridir. Bu işlevler [Varsayılan Oluşturucu](constructors-cpp.md#default_constructors), [yıkıcı](destructors-cpp.md), [kopya Oluşturucu ve kopya atama operatörü](copy-constructors-and-copy-assignment-operators-cpp.md)ve [taşıma Oluşturucu ve taşıma atama işleçleridir](move-constructors-and-move-assignment-operators-cpp.md). Sınıfınız bir veya daha fazla özel üye işlevi tanımmıyorsa, derleyici dolaylı olarak kullanılan işlevleri bildirebilir ve tanımlayabilir. Derleyicinin ürettiği uygulamalar *varsayılan* özel üye işlevleri olarak adlandırılır. Derleyici gerekmiyorsa, işlevler oluşturmaz.

Varsayılan bir özel üye işlevini açık bir şekilde **= Default** anahtar sözcüğünü kullanarak bildirebilirsiniz. Bu, derleyicinin işlevi yalnızca gerekirse, işlevin hiç bildirilmemiş gibi aynı şekilde tanımlamasına neden olur.

Bazı durumlarda, derleyici, tanımlanmamış ve bu nedenle çağrılabilir olmayan *Silinmiş* özel üye işlevleri oluşturabilir. Bu, sınıf üzerinde belirli bir özel üye işlevine yapılan çağrının anlamlı olmadığı ve sınıfın diğer özellikleri verildiği durumlarda meydana gelebilir. Özel bir üye işlevinin otomatik olarak oluşturulmasını açıkça engellemek için, **= Delete** anahtar sözcüğünü kullanarak silinmiş olarak bildirebilirsiniz.

Derleyici, yalnızca başka bir Oluşturucu bildirmediği zaman bağımsız değişken alan bir Oluşturucu olan *varsayılan bir Oluşturucu* oluşturur. Yalnızca parametre alan bir Oluşturucu bildirdiyseniz, varsayılan bir Oluşturucu çağırmayı deneyen kod derleyicinin bir hata mesajı üretmesine neden olur. Derleyicinin ürettiği varsayılan Oluşturucu, nesnesinin basit üye temelli [varsayılan başlatmasını](initializers.md#default_initialization) gerçekleştirir. Varsayılan başlatma, tüm üye değişkenlerini belirsiz bir durumda bırakır.

Varsayılan yıkıcı nesnenin üye Wise yok edilmesini gerçekleştirir. Yalnızca bir taban sınıf yıkıcısı sanal ise sanal olur.

Varsayılan kopyalama ve taşıma oluşturma ve atama işlemleri, üye temelli bit desenli kopyalar veya statik olmayan veri üyelerinin taşınmasını gerçekleştirir. Taşıma işlemleri yalnızca yıkıcı veya taşıma ya da kopyalama işlemleri bildirildiğinde oluşturulur. Varsayılan kopya Oluşturucu yalnızca hiçbir kopya Oluşturucu bildirildiğinde oluşturulur. Bir taşıma işlemi bildirilirse, örtülü olarak silinir. Varsayılan bir kopya atama işleci yalnızca hiçbir kopyalama atama işleci açıkça bildirildiğinde oluşturulur. Bir taşıma işlemi bildirilirse, örtülü olarak silinir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](cpp-language-reference.md)
