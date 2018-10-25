---
title: 'Pano: Veri kopyalama ve yapıştırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f4a3ba23fbf6e9465d78b04fcd79758c7cae525
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060240"
---
# <a name="clipboard-copying-and-pasting-data"></a>Pano: Veri Kopyalama ve Yapıştırma

Bu konu, kopyalama ve OLE uygulamanızda panodan yapıştırma uygulamak gerekli en düşük iş açıklar. Okumanızı tavsiye edilir [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) devam etmeden önce konuları.

Kopyalama veya yapıştırarak uygulamadan önce ilk Düzen menüsünde Kopyala, Kes ve Yapıştır seçeneklerini işlemek için işlevleri sağlamanız gerekir.

##  <a name="_core_copying_or_cutting_data"></a> Kopyalama veya kesme verileri

#### <a name="to-copy-data-to-the-clipboard"></a>Verileri panoya kopyalamak için

1. Kopyalanacak verileri yerel veriler veya gömülü veya bağlantılı bir öğe olup olmadığını belirler.

   - Veri gömülü veya bağlantılı bir işaretçi alma `COleClientItem` seçildi bir nesne.

   - Verileri yerel olarak ve bir sunucu uygulaması ise, türetilen yeni nesne oluşturma `COleServerItem` seçilen verileri içeren. Aksi takdirde, oluşturun bir `COleDataSource` veri nesnesi.

1. Seçilen öğenin arama `CopyToClipboard` üye işlevi.

1. Kullanıcı, bir kopyalama işlemi yerine bir kesme işlemi seçerseniz, seçilen verileri uygulamanızdan silin.

Bu sıralı bir örneğini görmek için bkz: `OnEditCut` ve `OnEditCopy` işlevlerde MFC OLE örnek programlar [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md). 1. adım zaten tamamlandı, bu nedenle bu örnekleri şu anda seçili veri işaretçisi korumak unutmayın.

##  <a name="_core_pasting_data"></a> Veri yapıştırma

Veri yapıştırma uygulamanıza veri yapıştırma içinde kullanılacak biçimi seçin gerektiğinden kopyalayarak değerinden daha karmaşık bir işlemdir.

#### <a name="to-paste-data-from-the-clipboard"></a>Pano verileri yapıştırmak için

1. View sınıfında, uygulama `OnEditPaste` Düzenle Menüsü'nden Yapıştır seçeneği seçerek kullanıcılar işlemek için.

1. İçinde `OnEditPaste` işlev, oluşturun bir `COleDataObject` nesne ve çağrı kendi `AttachClipboard` Panodaki veriler için bu nesneyi bağlamak için üye işlevi.

1. Çağrı `COleDataObject::IsDataAvailable` belirli bir biçimde kullanılabilir olup olmadığını denetlemek için.

   Alternatif olarak, kullanabileceğiniz `COleDataObject::BeginEnumFormats` bir uygulamanız için en uygun bulana kadar diğer biçimleri için aranacak.

1. Yapıştırma biçimi gerçekleştirin.

Bunun nasıl çalıştığına ilişkin bir örnek için bkz: `OnEditPaste` MFC OLE örnek programlardan içinde tanımlanan görünüm sınıflardaki üye işlevleri [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md).

> [!TIP]
>  Yapıştırma işlemi kendi işlevine ayırma ana avantajı, bir Sürükle ve bırak işlemi sırasında uygulamanızdaki veri bırakıldığında aynı Yapıştır kodu kullanılabilir ' dir. OCLIENT ve HIERSVR, olduğu gibi `OnDrop` işlevi ayrıca çağırabilir `DoPasteItem`, yapıştır işlemlerini uygulamak için yazılmış kodu yeniden kullanma.

Düzen menüsündeki Özel Yapıştır seçeneği işlemek için Ek Yardım konusuna [ole'deki iletişim kutuları](../mfc/dialog-boxes-in-ole.md).

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)

- [OLE veri nesneleri ve veri kaynaklarını ve Tekdüzen veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)

- [OLE sürükleme ve bırakma](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pano: OLE Pano Mekanizmasını Kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

