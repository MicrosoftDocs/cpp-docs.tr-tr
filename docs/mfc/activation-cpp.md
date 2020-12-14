---
description: 'Daha fazla bilgi edinin: etkinleştirme (C++)'
title: Etkinleştirme (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
ms.openlocfilehash: 726c64344f684c8ca9e79d9296daea80882af08f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197731"
---
# <a name="activation-c"></a>Etkinleştirme (C++)

Bu makalede, OLE öğelerinin görsel düzenlemede etkinleştirme rolü açıklanmaktadır. Bir Kullanıcı bir kapsayıcı belgeye bir OLE öğesi katıştırdıktan sonra, kullanılması gerekebilir. Bunu yapmak için kullanıcı öğeyi çift tıklatır ve bu öğeyi etkinleştirir. Etkinleştirme için en sık kullanılan etkinlik düzenlemedir. Birçok geçerli OLE öğesi, düzenlenmek üzere etkinleştirildiğinde, geçerli çerçeve penceresindeki menülerin ve araç çubuklarının öğeyi oluşturan sunucu uygulamasına ait olanları yansıtacak şekilde değişmesine neden olur. Yerinde etkinleştirme olarak bilinen bu davranış, kullanıcının kapsayıcı belgenin penceresinden çıkmadan bir Birleşik belgedeki herhangi bir katıştırılmış öğeyi düzenlemesine izin verir.

Katıştırılmış OLE öğelerini ayrı bir pencerede düzenlemek de mümkündür. Kapsayıcı veya sunucu uygulaması yerinde etkinleştirmeyi desteklemiyorsa, bu durum gerçekleşir. Bu durumda, Kullanıcı katıştırılmış bir öğeyi çift tıkladığında, sunucu uygulaması ayrı bir pencerede başlatılır ve katıştırılmış öğe kendi belgesi olarak görünür. Kullanıcı Bu penceredeki öğeyi düzenler. Düzen tamamlandığında, Kullanıcı sunucu uygulamasını kapatır ve kapsayıcı uygulamasına geri döner.

Alternatif olarak, Kullanıcı **düzenleme** menüsünde **\<object> Aç** komutuyla "düzenleme aç" seçeneğini belirleyebilir. Bu, nesneyi ayrı bir pencerede açar.

> [!NOTE]
> Katıştırılmış öğelerin ayrı bir pencerede düzenlenmesinin, OLE sürüm 1 ' deki standart davranışı ve bazı OLE uygulamaları yalnızca bu Düzenle stilini destekleyebilir.

Yerinde etkinleştirme belge oluşturmaya yönelik belge odaklı bir yaklaşım yükseltir. Kullanıcı, bileşik bir belgeyi uygulamalar arasında geçiş yapmadan tek bir varlık olarak kabul edebilir. Ancak yerinde etkinleştirme, bağlantılı öğeler için değil, yalnızca katıştırılmış öğeler için kullanılır: ayrı bir pencerede düzenlenmeleri gerekir. Bunun nedeni, bağlantılı bir öğenin gerçekten farklı bir yerde depolanmasıdır. Bağlı bir öğenin düzenlenmesinin, verilerin gerçek bağlamı içinde, yani verilerin depolandığı yerde yer alır. Bağlı bir öğeyi ayrı bir pencerede düzenlediğinizde, kullanıcılar verilerin başka bir belgeye ait olduğunu anımsatır.

MFC iç içe yerleştirilmiş yerinde etkinleştirmeyi desteklemez. Bir kapsayıcı/sunucu uygulaması derleyebilir ve bu kapsayıcı/sunucu başka bir kapsayıcıya katıştırılmışsa ve yerinde etkinleştirildiyse, bu, içinde gömülü nesneleri yerinde etkinleştirir.

Kullanıcı çift tıkladığında eklenmiş bir öğeye ne olur, öğe için tanımlanan fiillere bağlıdır. Daha fazla bilgi için bkz. [etkinleştirme: fiiller](activation-verbs.md).

## <a name="see-also"></a>Ayrıca bkz.

[OLE](ole-in-mfc.md)<br/>
[Kapsayıcılar](containers.md)<br/>
[Sunucular](servers.md)
