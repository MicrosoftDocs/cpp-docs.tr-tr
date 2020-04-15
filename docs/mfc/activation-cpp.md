---
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
ms.openlocfilehash: 9f3fba71002a19a0be0e3429a0faeeefb7c65197
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354178"
---
# <a name="activation-c"></a>Etkinleştirme (C++)

Bu makalede, OLE öğelerinin görsel düzenleme etkinleştirme rolü açıklanmaktadır. Bir kullanıcı bir ole öğesini kapsayıcı belgesine katışarttıktan sonra kullanılması gerekebilir. Bunu yapmak için, kullanıcı öğeyi çift tıklatıyor ve bu öğeyi etkinleştirir. Etkinleştirme için en sık karşılaşılan etkinlik düzenlemedir. Düzenleme için etkinleştirildiğinde, geçerli çerçeve penceresindeki menülerin ve araç çubuklarının öğeyi oluşturan sunucu uygulamasına ait olanları yansıtacak şekilde değişmesine neden olan birçok geçerli OLE öğesi. Yerinde etkinleştirme olarak bilinen bu davranış, kullanıcının kapsayıcı belgenin penceresinden çıkmadan bileşik belgedeki katışmış öğeyi yeniden düzenledirmesine olanak tanır.

Katıştırılmış OLE öğelerini ayrı bir pencerede de döşeyen mümkündür. Kapsayıcı veya sunucu uygulaması yerinde etkinleştirme desteklemiyorsa bu durum gerçekleşir. Bu durumda, kullanıcı katıştırılmış bir öğeyi çift tıklattığında, sunucu uygulaması ayrı bir pencerede başlatılır ve közlenmiş öğe kendi belgesi olarak görünür. Kullanıcı bu penceredeki öğeyi yeniden dikir. Düzenleme tamamlandığında, kullanıcı sunucu uygulamasını kapatır ve kapsayıcı uygulamasına geri döner.

Alternatif olarak, kullanıcı **Düzenle** menüsündeki aç komutu ** \<> nesneyle** "düzenlemeyi aç"ı seçebilir. Bu, nesneyi ayrı bir pencerede açar.

> [!NOTE]
> Katıştırılmış öğeleri ayrı bir pencerede düzenlemek OLE'nin sürüm 1'inde standart davranıştı ve bazı OLE uygulamaları yalnızca bu düzenleme stilini destekleyebilir.

Yerinde etkinleştirme, belge oluşturma için belge merkezli bir yaklaşımı teşvik eder. Kullanıcı, bileşik bir belgeyi uygulamalar arasında geçiş yapmadan üzerinde çalışarak tek bir varlık olarak işleyebilir. Ancak, yerinde etkinleştirme yalnızca bağlı öğeler için değil, gömülü öğeler için kullanılır: bunlar ayrı bir pencerede düzenlenmelidir. Bunun nedeni, bağlantılı bir öğenin aslında farklı bir yerde depolanmış olmasıdır. Bağlı bir öğenin düzenlenmesi, verilerin gerçek bağlamı içinde, yani verilerin depolandığı yer içinde gerçekleşir. Bağlantılı bir öğeyi ayrı bir pencerede düzenlemek, kullanıcıya verilerin başka bir belgeye ait olduğunu hatırladır.

MFC iç içe yer etkinleştirme desteklemez. Bir kapsayıcı/sunucu uygulaması oluşturursanız ve bu kapsayıcı/sunucu başka bir kapsayıcıya gömülüyse ve yerinde etkinleştirilmişse, içine katıştırılmış nesneleri yerinde etkinleştiremez.

Kullanıcı çift tıklatıldığında katıştırılmış bir öğeye ne olur, öğe için tanımlanan fiillere bağlıdır. Bilgi için, [bkz. Etkinleştirme: Fiiller](../mfc/activation-verbs.md).

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Sunucular](../mfc/servers.md)
