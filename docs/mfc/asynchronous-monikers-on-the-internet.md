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
ms.openlocfilehash: 74add1ad894f883c67eefab888898c0abf518b83
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625028"
---
# <a name="asynchronous-monikers-on-the-internet"></a>Internet'teki Zaman Uyumsuz Adlar

Internet, yavaş ağ erişimi nedeniyle uygulama tasarımında yeni yaklaşımlar gerektirir. Uygulamalar, kullanıcı arabiriminden kaçınılması için ağ erişimi zaman uyumsuz olarak gerçekleştirmelidir. MFC sınıfı [CAsyncMonikerFile](reference/casyncmonikerfile-class.md) , dosyaları indirmek için zaman uyumsuz destek sağlar.

Zaman uyumsuz bilinen adlar sayesinde COM uygulamanızı Internet üzerinden zaman uyumsuz olarak indirmek ve bit eşlemler ve VRML nesneleri gibi büyük nesnelerin aşamalı işlemesini sağlamak için genişletebilirsiniz. Zaman uyumsuz bilinen adlar bir ActiveX denetim özelliğini veya Internet üzerindeki bir dosyayı, Kullanıcı arabiriminin yanıtını engellemeden indirilebilecek şekilde etkinleştirir.

## <a name="advantages-of-asynchronous-monikers"></a>Zaman uyumsuz bilinen adların avantajları

Zaman uyumsuz bilinen adları şu şekilde kullanabilirsiniz:

- Kodu ve dosyaları engellenmeden indirin.

- ActiveX denetimlerinde özellikleri engellenmeksizin indirin.

- Yüklemenin ilerlemesini alma bildirimleri alın.

- İlerleme durumunu ve hazırlık durumu bilgilerini izleyin.

- Kullanıcıya ilerleme durumuyla ilgili durum bilgilerini sağlayın.

- Kullanıcının herhangi bir zamanda indirmeyi iptal edebilmesini sağlar.

## <a name="mfc-classes-for-asynchronous-monikers"></a>Zaman uyumsuz adlar için MFC sınıfları

[CAsyncMonikerFile](reference/casyncmonikerfile-class.md) , [CMonikerFile](reference/cmonikerfile-class.md)'den türetilir ve bu da [copastreamfile](reference/colestreamfile-class.md)öğesinden türetilir. Bir `COleStreamFile` nesne veri akışını temsil eder; bir `CMonikerFile` nesne, `IMoniker` verileri almak için bir kullanır ve bir `CAsyncMonikerFile` nesnesi bunu zaman uyumsuz olarak yapar.

Zaman uyumsuz adlar öncelikle Internet etkin uygulamalar ve ActiveX denetimlerinde, dosya aktarımları sırasında yanıt veren bir kullanıcı arabirimi sağlamak için kullanılır. Bunun ana örneği, ActiveX denetimleri için zaman uyumsuz özellikler sağlamak üzere [CDataPathProperty](reference/cdatapathproperty-class.md) öğesinin kullanılması örneğidir.

## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>ActiveX denetimlerinde veri yolları için MFC sınıfları

MFC sınıfları `CDataPathProperty` ve [CCachedDataPathProperty](reference/ccacheddatapathproperty-class.md) , zaman uyumsuz olarak yüklenebilecek ActiveX denetim özelliklerini uygular. Zaman uyumsuz özellikler, zaman uyumlu başlatma işleminden sonra yüklenir. Zaman uyumsuz ActiveX denetimleri, uzun bir özellik değişim işlemi sırasında yeni verilerin kullanılabilirliğini göstermek için sürekli olarak bir geri çağırma çağırır.

`CDataPathProperty`, öğesinden türetilir `CAsyncMonikerFile` . `CCachedDataPathProperty`, öğesinden türetilir `CDataPathProperty` . ActiveX denetimlerinize zaman uyumsuz özellikler uygulamak için, veya ' den bir sınıf türetirsiniz `CDataPathProperty` `CCachedDataPathProperty` ve [OnDataAvailable](reference/casyncmonikerfile-class.md#ondataavailable) almak istediğiniz diğer bildirimleri ve geçersiz kılın.

#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Zaman uyumsuz bilinen adlar kullanarak bir dosyayı indirmek için

1. [CAsyncMonikerFile](reference/casyncmonikerfile-class.md)öğesinden türetilen bir sınıf bildirin.

1. Verileri göstermek için [OnDataAvailable](reference/casyncmonikerfile-class.md#ondataavailable) öğesini geçersiz kılın.

1. [OnProgress](reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](reference/casyncmonikerfile-class.md#onstartbinding)ve [OnStopBinding](reference/casyncmonikerfile-class.md#onstopbinding)dahil diğer üye işlevlerini geçersiz kılın.

1. Bu sınıfın bir örneğini bildirin ve URL 'Leri açmak için kullanın.

ActiveX denetiminde zaman uyumsuz olarak indirme hakkında daha fazla bilgi için bkz. [Internet 'Teki ActiveX denetimleri](activex-controls-on-the-internet.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Görevleri](mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](mfc-internet-programming-basics.md)
