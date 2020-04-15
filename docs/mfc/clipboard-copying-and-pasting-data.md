---
title: 'Pano: Veri Kopyalama ve Yapıştırma'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
ms.openlocfilehash: 74348dd3e790cceada9aafd718464694997316ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374565"
---
# <a name="clipboard-copying-and-pasting-data"></a>Pano: Veri Kopyalama ve Yapıştırma

Bu konu, OLE uygulamanızda Pano'ya kopyalama ve yapıştırma uygulamak için gereken minimum çalışmayı açıklar. İşleme başlamadan önce [Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) konularını okumanız önerilir.

Kopyalama veya yapıştırma uygulamadan önce, Edit menüsündeki Kopyala, Kes ve Yapıştır seçeneklerini işlemek için işlevler sağlamanız gerekir.

## <a name="copying-or-cutting-data"></a><a name="_core_copying_or_cutting_data"></a>Verileri Kopyalama veya Kesme

#### <a name="to-copy-data-to-the-clipboard"></a>Verileri Panoya kopyalamak için

1. Kopyalanacak verilerin yerel veri mi yoksa katıştırılmış veya bağlantılı bir öğe mi olduğunu belirleyin.

   - Veriler katıştırılmış veya bağlıysa, `COleClientItem` seçilen nesneye bir işaretçi edinin.

   - Veriler yerelse ve uygulama bir sunucuysa, seçili `COleServerItem` verileri içeren yeni bir nesne oluşturun. Aksi takdirde, `COleDataSource` veriler için bir nesne oluşturun.

1. Seçili öğenin `CopyToClipboard` üye işlevini arayın.

1. Kullanıcı Kopyalama işlemi yerine bir Kesme işlemi seçtiyse, uygulamanızdan seçili verileri silin.

Bu dizinin bir örneğini görmek `OnEditCut` `OnEditCopy` için, MFC OLE örnek programları [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR'daki](../overview/visual-cpp-samples.md)işlevleri ve işlevleri görün. Bu örneklerin şu anda seçili verilere işaretçisi koruduğunu, bu nedenle adım 1'in zaten tamamlandığını unutmayın.

## <a name="pasting-data"></a><a name="_core_pasting_data"></a>Verileri Yapıştırma

Verileri yapıştırmak, verileri uygulamanıza yapıştırmada kullanılacak biçimi seçmeniz gerektiğinden kopyalamaktan daha karmaşıktır.

#### <a name="to-paste-data-from-the-clipboard"></a>Panodan veri yapıştırmak için

1. Görünüm sınıfınızda, `OnEditPaste` Edit menüsünden Yapıştır seçeneğini seçen kullanıcıları işlemek için uygulayın.

1. İşlevde, `OnEditPaste` bir `COleDataObject` nesne oluşturun `AttachClipboard` ve bu nesneyi Pano'daki verilere bağlamak için üye işlevini çağırın.

1. Belirli `COleDataObject::IsDataAvailable` bir biçimin kullanılabilir olup olmadığını kontrol etmek için arayın.

   Alternatif olarak, uygulamanız için en uygun biçimleri bulana kadar diğer biçimleri aramak için kullanabilirsiniz. `COleDataObject::BeginEnumFormats`

1. Biçimin yapıştırını gerçekleştirin.

Bunun nasıl çalıştığına bir örnek olarak, `OnEditPaste` MFC OLE örnek programlarında tanımlanan görünüm sınıflarında üye işlevlerin uygulanmasına bakın [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR.](../overview/visual-cpp-samples.md)

> [!TIP]
> Yapıştırma işlemini kendi işlevine ayırmanın en büyük yararı, sürükle ve bırak işlemi sırasında uygulamanızda veriler bırakıldığında aynı yapıştırma kodunun kullanılabilmesidir. OCLIENT ve HIERSVR'da `OnDrop` olduğu gibi, işleviniz yapıştır işlemleri uygulamak için yazılan kodu yeniden kullanarak da arayabilir. `DoPasteItem`

Edit menüsünde Özel Yapıştır seçeneğini işlemek için [OLE'deki](../mfc/dialog-boxes-in-ole.md)konuya bakın İletişim Kutuları.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Diğer biçimler ekleme](../mfc/clipboard-adding-other-formats.md)

- [OLE veri nesneleri ve veri kaynakları ve tek tip veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)

- [OLE sürükle ve bırak](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano: OLE Pano Mekanizmasını Kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
