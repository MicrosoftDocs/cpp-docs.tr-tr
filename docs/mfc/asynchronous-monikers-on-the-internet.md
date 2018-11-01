---
title: Internet'teki Zaman Uyumsuz Adlar
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
ms.openlocfilehash: 63bdc8372223075804d8c710909909382167b2c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591301"
---
# <a name="asynchronous-monikers-on-the-internet"></a>Internet'teki Zaman Uyumsuz Adlar

Internet uygulama tasarımı için yeni yaklaşımlar nedeniyle, yavaş ağ erişimi gerektirir. Uygulamalar, zaman uyumsuz olarak kullanıcı arabirimi bekletilen önlemek için ağ erişimi gerçekleştirmeniz gerekir. MFC sınıfı [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) dosyaları indirme için zaman uyumsuz destek sağlar.

Zaman uyumsuz adlar ile Internet üzerinden zaman uyumsuz olarak indirmek ve bit eşlemler gibi büyük nesneler ve VRML nesnelerin aşamalı işleme sağlamak için COM uygulamanızı genişletebilirsiniz. Zaman uyumsuz adlar kullanıcı arabiriminin yanıt engellemeden yüklenmek üzere Internet üzerindeki bir dosya ya da ActiveX denetimi özelliğini etkinleştirin.

## <a name="advantages-of-asynchronous-monikers"></a>Zaman uyumsuz adlar avantajları

Zaman uyumsuz adlar için kullanabilirsiniz:

- Kod ve dosyaları engellemeden indirin.

- ActiveX denetimlerindeki özellikler engellemeden indirin.

- İndirme ilerleme bildirimleri alırsınız.

- İlerleme ve hazır durumu bilgilerini izleyin.

- İlerleme durumu hakkında kullanıcıya durum bilgileri sağlar.

- Karşıdan yükleme dilediğiniz zaman iptal izin verin.

## <a name="mfc-classes-for-asynchronous-monikers"></a>MFC sınıfları için zaman uyumsuz adlar

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) türetilir [CMonikerFile](../mfc/reference/cmonikerfile-class.md), hangi sırayla türetilmiş olan [COleStreamFile](../mfc/reference/colestreamfile-class.md). A `COleStreamFile` bir veri akışı; bir nesneyi temsil eder `CMonikerFile` nesnesini kullanan bir `IMoniker` verileri almak için ve bir `CAsyncMonikerFile` nesne mu bunu zaman uyumsuz olarak.

Zaman uyumsuz adlar, öncelikle Internet özellikli uygulamalar ve ActiveX denetimleri, dosya aktarımlarında duyarlı kullanıcı arabirimi sağlamak için kullanılır. Bu prime örneği kullanımıdır [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) ActiveX denetimleri için zaman uyumsuz özellikler sağlamak için.

## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>Veri yolları ActiveX denetimleri için MFC sınıfları

MFC sınıfları `CDataPathProperty` ve [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) zaman uyumsuz olarak yüklenebilen ActiveX denetim özelliği uygular. Zaman uyumsuz özellikler, zaman uyumlu başlatma sonra yüklenir. Zaman uyumsuz ActiveX denetimleri, sürekli kullanılabilirlik yeni verilerin uzun özelliği değişimi sırasında belirtmek için bir geri çağırma.

`CDataPathProperty` türetilen `CAsyncMonikerFile`. `CCachedDataPathProperty` türetilen `CDataPathProperty`. Zaman uyumsuz özellikler, ActiveX denetimlerinde uygulamak için öğesinden bir sınıf türetin `CDataPathProperty` veya `CCachedDataPathProperty`ve geçersiz kılma [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) ve almak istediğiniz diğer bildirimleri.

#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Zaman uyumsuz adlar kullanarak bir dosyayı indirmek için

1. Türetilen bir sınıf bildirme [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

1. Geçersiz kılma [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) verileri görüntülemek için.

1. Dahil olmak üzere diğer üye işlevlerini geçersiz kılma [OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding), ve [OnStopBinding](../mfc/reference/casyncmonikerfile-class.md#onstopbinding).

1. Bu sınıfın örneği bildirin ve URL'leri açmasına izin kullanın.

Zaman uyumsuz olarak ActiveX denetiminde yükleme hakkında daha fazla bilgi için bkz: [Internet'te ActiveX denetimleri](../mfc/activex-controls-on-the-internet.md).

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

