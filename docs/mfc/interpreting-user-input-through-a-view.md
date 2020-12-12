---
description: 'Hakkında daha fazla bilgi edinin: bir görünüm aracılığıyla Kullanıcı girişini yorumlama'
title: Bir Görünümü Kullanarak Kullanıcı Girişini Yorumlama
ms.date: 11/04/2016
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
ms.openlocfilehash: f3442a13bc60b7424840e23673806c1e5120c4ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335839"
---
# <a name="interpreting-user-input-through-a-view"></a>Bir Görünümü Kullanarak Kullanıcı Girişini Yorumlama

Görünüm tanıtıcısının diğer üye işlevleri ve tüm kullanıcı girişlerini yorumlar. İşlem için görünüm sınıfınıza ileti işleyici üye işlevlerini genellikle tanımlayacaksınız:

- Fare ve klavye eylemleri tarafından oluşturulan Windows [iletileri](messages.md) .

- Menüler, araç çubuğu düğmeleri ve kısayol tuşlarının [komutları](user-interface-objects-and-command-ids.md) .

Bu ileti işleyici üye işlevleri, verileri Pano 'ya ve Panodan taşıma dahil olmak üzere veri girişi, seçimi veya düzenlemesi olarak aşağıdaki eylemleri Yorumlar:

- Fare hareketleri ve tıklama, sürükme ve çift tıklama

- Basılan

- Menü komutları

Görünümün işleyeceği Windows iletileri uygulamanızın ihtiyaçlarına bağlıdır.

[Ileti işleme ve eşleme konuları](message-handling-and-mapping.md) menü öğelerinin ve diğer kullanıcı arabirimi nesnelerinin komutlara nasıl atanacağını ve komutların işleyici işlevlerine nasıl bağlanacağını açıklar. [Ileti işleme ve eşleme konuları](message-handling-and-mapping.md) , MFC 'nin komutları nasıl yönlendirdiğini ve bunlara yönelik işleyiciler içeren nesnelere nasıl standart Windows iletileri göndereceğini açıklar.

Örneğin, uygulamanızın görünümünde doğrudan fare çizimi uygulaması gerekebilir. Karalama örneği, bir çizgi segmentinin başlamasını, devam etmesini ve çizimini bitirmek için sırasıyla WM_LBUTTONDOWN, WM_MOUSEMOVE ve WM_LBUTTONUP iletilerinin nasıl işleneceğini gösterir. Öte yandan, bazen bir fare tıklamasını seçim olarak yorumlamanıza gerek duyabilirsiniz. Görünümlerinizin `OnLButtonDown` işleyici işlevi kullanıcının çizim yapıp kullanmadığını veya seçip seçmediğini belirleyebilir. Seçilirse, işleyici, görünümün görünümdeki bazı nesnelerin sınırları içinde olup olmadığını belirleyebilir ve bu durumda, nesneyi seçili olarak göstermek için görüntüle seçeneğini değiştirin.

Görünümü, pano kullanarak seçili verileri kesmek, kopyalamak, yapıştırmak veya silmek için düzenleme menüsünden olanlar gibi bazı menü komutlarını da işleyebilir. Bu tür bir işleyici, `CWnd` Seçili bir veri öğesini Pano 'ya veya Panodan aktarmak için bazı Pano ile ilgili üye işlevlerinden bir kısmını çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri kullanma](using-views.md)
