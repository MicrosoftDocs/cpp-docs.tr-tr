---
title: 'Pano: Diğer Biçimleri Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
ms.openlocfilehash: 6f4e159cc1b6918843d4a164dcca88500eb7b038
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374602"
---
# <a name="clipboard-adding-other-formats"></a>Pano: Diğer Biçimleri Ekleme

Bu konu, desteklenen biçimler listesini, özellikle OLE desteği için nasıl genişletiriz açıklar. Konu [Panosu: Verileri Kopyalama ve Yapıştırma,](../mfc/clipboard-copying-and-pasting-data.md) Panodan kopyalama ve yapıştırmayı desteklemek için gereken minimum uygulamayı açıklar. Tüm uyguladığınız buysa, Panoya yerleştirilen tek **biçimler CF_METAFILEPICT**, **CF_EMBEDSOURCE,** **CF_OBJECTDESCRIPTOR**, ve muhtemelen **CF_LINKSOURCE.** Çoğu uygulama, Pano'da bu üçünden daha fazla biçime ihtiyaç duyar.

## <a name="registering-custom-formats"></a><a name="_core_registering_custom_formats"></a>Özel Biçimleri Kaydetme

Kendi özel biçimlerinizi oluşturmak için, herhangi bir özel Pano biçimini kaydederken kullanacağınız yordamı uygulayın: biçimin adını **RegisterClipboardFormat** işlevine geçirin ve biçim kimliği olarak iade değerini kullanın.

## <a name="placing-formats-on-the-clipboard"></a><a name="_core_placing_formats_on_the_clipboard"></a>Panoya Biçim Yerleştirme

Panoya yerleştirilenlere daha fazla biçim eklemek için, türetilen sınıftaki `OnGetClipboardData` işlevi `COleClientItem` geçersiz `COleServerItem` kılmanız gerekir veya (kopyalanacak verilerin yerel olup olmadığına bağlı olarak). Bu işlevde, aşağıdaki yordamı kullanmanız gerekir.

#### <a name="to-place-formats-on-the-clipboard"></a>Biçimleri Panoya yerleştirmek için

1. Bir `COleDataSource` nesne oluşturun.

1. Bu veri kaynağını, yerel veri biçimlerinizi desteklenen biçimler listesine ekleyerek `COleDataSource::CacheGlobalData`ekleyen bir işleve geçirin.

1. Desteklemek istediğiniz her `COleDataSource::CacheGlobalData` standart biçimi arayarak standart biçimler ekleyin.

Bu teknik MFC OLE örnek programı [HIERSVR](../overview/visual-cpp-samples.md) `OnGetClipboardData` 'da kullanılır **(CServerItem** sınıfının üye işlevini inceleyin). HiERSVR başka standart biçimleri desteklemediği için bu örnekteki tek fark üçüncü adımın uygulanmamasıdır.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [OLE veri nesneleri ve veri kaynakları ve tek tip veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)

- [OLE sürükle ve bırak](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano: OLE Pano Mekanizmasını Kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
