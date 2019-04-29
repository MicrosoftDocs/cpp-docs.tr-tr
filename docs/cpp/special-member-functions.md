---
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
ms.openlocfilehash: 3b26628fd18749bd19819fe787888fd3264a79d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330986"
---
# <a name="special-member-functions"></a>Özel üye işlevleri

*Özel üye işlevleri* sınıfı (ya da yapı) bazı durumlarda, derleyicinin otomatik olarak sizin için oluşturur, üye işlevleri olan. Bu işlevler [varsayılan oluşturucu](constructors-cpp.md#default_constructors), [yok Edicisi](destructors-cpp.md), [kopya oluşturucu ve kopya atama işleci](copy-constructors-and-copy-assignment-operators-cpp.md)ve [taşıma oluşturucu ve taşıma atama işlecine](move-constructors-and-move-assignment-operators-cpp.md). Sınıfınızın bir veya daha fazla özel üye işlevleri tanımlamıyorsa, ardından derleyici örtük olarak bildirmek ve kullanılan işlevleri tanımlayın. Derleyici tarafından oluşturulan uygulamaları adlı *varsayılan* özel üye işlevleri. Bunlar gerekli değilse, derleyici işlevleri oluşturmaz.

Kullanarak açıkça varsayılan özel üye işlevini bildirebilirsiniz **= default** anahtar sözcüğü. Bu işlevi hiç bildirilmedi gibi yalnızca aynı şekilde gerekirse işlevi tanımlama derleyicinin neden olur.

Bazı durumlarda, derleyicinin oluşturabilir *silinmiş* özel üye işlevler, tanımlanan ve bu nedenle değil çağrılabilir değildir. Bu, burada bir sınıftaki belirli özel üye işlevi çağrısı sınıfın diğer özelliklerini verilen, anlam ifade etmez durumlarda gerçekleşebilir. Açıkça özel üye işlevini otomatik olarak oluşturulmasını önlemek için onu kullanarak silindi olarak bildirebilirsiniz **= Sil** anahtar sözcüğü.

Derleyicinin oluşturduğu bir *varsayılan oluşturucu*, yalnızca diğer bir oluşturucu bildirmemiş olduğunda hiçbir bağımsız değişken alan bir oluşturucu. Varsayılan oluşturucuyu çağırmak için çalışan kod, yalnızca parametreleri alan bir oluşturucu bildirirseniz, derleyici bir hata iletisi oluşturmak üzere neden olur. Derleyicinin ürettiği varsayılan oluşturucuyu member-wise basit gerçekleştirir [başlatma varsayılan](initializers.md#default_initialization) nesne. Varsayılan başlatma tüm üye değişkenleri belirsiz bir durumda bırakır.

Varsayılan yıkıcıdan nesnenin member-wise yok etme gerçekleştirir. Yalnızca bir temel sınıf yok edicisini sanal ise sanal.

Member-wise bit deseni varsayılan kopyalama ve taşıma oluşturma ve atama işlemleri gerçekleştirmek kopyalar veya statik olmayan veri üyelerine taşır. Herhangi bir yıkıcı veya taşıma veya kopyalama işlemleri bildirildiğinde işlemleri yalnızca oluşturulan taşıyın. Hiçbir kopya Oluşturucusu bildirildiğinde varsayılan bir kopya Oluşturucu yalnızca oluşturulur. Bir taşıma işlemi bildirilirse, örtük olarak silindi. Varsayılan kopya atama işleci, yalnızca hiçbir kopya atama işleci açıkça bildirildiğinde oluşturulur. Bir taşıma işlemi bildirilirse, örtük olarak silindi.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](cpp-language-reference.md)