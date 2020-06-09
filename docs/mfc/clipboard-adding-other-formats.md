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
ms.openlocfilehash: 52089364a6be423c69a7031cd0d99e1924de1444
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626070"
---
# <a name="clipboard-adding-other-formats"></a>Pano: Diğer Biçimleri Ekleme

Bu konu, özellikle OLE desteği için desteklenen biçimlerin listesini genişletmeyi açıklamaktadır. [Pano: veri kopyalama ve yapıştırma](clipboard-copying-and-pasting-data.md) Pano 'dan kopyalamayı ve yapıştırmayı desteklemek için gereken en düşük uygulamayı tanımlar. Bu tümü uygularsanız, panoya yerleştirilmiş olan tek Biçim **CF_METAFILEPICT**, **cf_embedsource**, **CF_OBJECTDESCRIPTOR**ve muhtemelen **CF_LINKSOURCE**. Çoğu uygulama, panoda bu üçünden daha fazla biçime sahip olacaktır.

## <a name="registering-custom-formats"></a><a name="_core_registering_custom_formats"></a>Özel biçimleri kaydetme

Kendi özel biçimlerinizi oluşturmak için özel Pano biçimini kaydederken kullandığınız yordamın aynısını izleyin: biçimin adını **RegisterClipboardFormat** işlevine geçirin ve dönüş DEĞERINI biçim kimliği olarak kullanın.

## <a name="placing-formats-on-the-clipboard"></a><a name="_core_placing_formats_on_the_clipboard"></a>Biçimleri Panoya yerleştirme

Panoya yerleştirilenlere daha fazla biçim eklemek için, ya `OnGetClipboardData` da `COleClientItem` `COleServerItem` (kopyalanacak verilerin yerel olup olmadığına bağlı olarak) türetilmiş sınıftaki işlevi geçersiz kılmanız gerekir. Bu işlevde, aşağıdaki yordamı kullanmanız gerekir.

#### <a name="to-place-formats-on-the-clipboard"></a>Biçimleri panoya yerleştirmek için

1. Bir `COleDataSource` nesne oluşturun.

1. Bu veri kaynağını, ' i çağırarak, desteklenen biçimlerin listesine yerel veri biçimlerinizi ekleyen bir işleve geçirin `COleDataSource::CacheGlobalData` .

1. Desteklemek istediğiniz her standart biçimi çağırarak standart biçimler ekleyin `COleDataSource::CacheGlobalData` .

Bu teknik MFC OLE örnek programı [Hiersvr](../overview/visual-cpp-samples.md) ' de kullanılır ( `OnGetClipboardData` **CServerItem** sınıfının üye işlevini inceleyin). Bu örnekteki tek fark, HIERSVR diğer standart biçimleri desteklediğinden, üçüncü adım uygulanmaz.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [OLE veri nesneleri ve veri kaynakları ve Tekdüzen veri aktarımı](data-objects-and-data-sources-ole.md)

- [OLE sürükle ve bırak](drag-and-drop-ole.md)

- [OLE](ole-background.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano: OLE Pano Mekanizmasını Kullanma](clipboard-using-the-ole-clipboard-mechanism.md)
