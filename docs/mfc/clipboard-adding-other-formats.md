---
title: 'Pano: Diğer biçimleri ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
ms.openlocfilehash: 182abe71ccc9552c113ebb114b4351178e48b096
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766853"
---
# <a name="clipboard-adding-other-formats"></a>Pano: Diğer biçimleri ekleme

Bu konuda özellikle OLE desteği için desteklenen biçimler listesini genişletin açıklanmaktadır. Konu [Pano: Kopyalama ve yapıştırma veri](../mfc/clipboard-copying-and-pasting-data.md) kopyalama ve yapıştırma panodan desteklemek için gereken en düşük uygulamasını açıklar. Bu tüm uygulamanız ise, panoya yerleştirilen yalnızca biçimler **CF_METAFILEPICT**, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**ve büyük olasılıkla **CF_LINKSOURCE**. Çoğu uygulama, bu üç Pano üzerinde daha fazla biçiminden gerekir.

##  <a name="_core_registering_custom_formats"></a> Özel kayıt biçimleri

Kendi özel biçimler oluşturmak için özel bir pano biçimi kaydolurken kullandığınız yordamın aynısını izleyin: biçimine adını geçirin **RegisterClipboardFormat** işlev ve dönüş değerinin biçimi ID olarak kullan

##  <a name="_core_placing_formats_on_the_clipboard"></a> Pano'ya yerleştirme biçimleri

Bu panoya yerleştirilen diğer biçimler eklemek için geçersiz kılmanız gerekir `OnGetClipboardData` işlevi öğesinden türetilmiş sınıftaki `COleClientItem` veya `COleServerItem` (kopyalanacak verileri yerel olup olmamasına bağlı olarak). Bu işlevde harcanan, aşağıdaki yordamı kullanmanız gerekir.

#### <a name="to-place-formats-on-the-clipboard"></a>Panodaki biçimleri yerleştirmek için

1. Oluşturma bir `COleDataSource` nesne.

1. Bu veri kaynağı, yerel veri biçimleri çağırarak desteklenen biçimlerde listesine ekleyen bir işlev geçirmek `COleDataSource::CacheGlobalData`.

1. Çağırarak Standard biçimleri ekleme `COleDataSource::CacheGlobalData` desteklemek istediğiniz her bir standart biçim için.

MFC OLE örnek program bu yöntem kullanılır [HIERSVR](../overview/visual-cpp-samples.md) (inceleyin `OnGetClipboardData` üye işlevinin **CServerItem** sınıfı). Bu örnekte tek fark, herhangi bir standart biçim HIERSVR desteklediği için bu üç adımı uygulanmadı.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [OLE veri nesneleri ve veri kaynaklarını ve Tekdüzen veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)

- [OLE sürükleme ve bırakma](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano: OLE Pano mekanizmasını kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
