---
title: 'Sürükle ve Bırak: Özelleştirme'
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
ms.openlocfilehash: d97bebce3ec7935dba7a9eca02a21be749efbec7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494297"
---
# <a name="drag-and-drop-customizing"></a>Sürükle ve Bırak: Özelleştirme

Sürükle ve bırak özelliğinin varsayılan uygulama, çoğu uygulama için yeterlidir. Ancak, bazı uygulamaların standart Bu davranışın değiştirilmesi gerekebilir. Bu makalede, bu varsayılan ayarları değiştirmek için gerekli adımları açıklanmaktadır. Ayrıca, bileşik belgeler bırakma kaynağı olarak desteklemeyen uygulamalar oluşturmak için bu tekniği kullanabilirsiniz.

Standart OLE sürükle ve bırak davranışını özelleştirme veya olmayan OLE uygulama varsa oluşturmalısınız bir `COleDataSource` verileri içeren nesne. Kullanıcı bir Sürükle ve bırak işlemi başlatıldığında, kodunuzu çağırmalıdır `DoDragDrop` sürükle ve bırak işlemleri destekleyen diğer sınıfları yerine bu nesne bir işlevden.

İsteğe bağlı olarak oluşturabileceğiniz bir `COleDropSource` bırakma denetlemenizi ve bazı işlevlerini değiştirmek istediğiniz davranışı türüne bağlı olarak geçersiz kılma nesne. Bu açılan kaynaklı bir nesne sonra geçirilen `COleDataSource::DoDragDrop` bu işlevlerin varsayılan davranışı değiştirmek için. Bu farklı seçenekler, bir büyük ölçüde esneklik uygulamanızda sürükle ve bırak işlemleri nasıl destek sağlar. Veri kaynakları hakkında daha fazla bilgi için bkz [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md).

Sürükle ve bırak işlemleri özelleştirmek için aşağıdaki işlevleri geçersiz kılabilirsiniz:

|Geçersiz kıl|Özelleştirmek için|
|--------------|------------------|
|`OnBeginDrag`|Çağırdıktan sonra nasıl sürükleyerek başlatılır `DoDragDrop`.|
|`GiveFeedback`|Farklı bir bırakma sonuçları için imlecin görünümü gibi görsel geri bildirim.|
|`QueryContinueDrag`|Bir Sürükle ve bırak işleminin sonlandırılması. Bu işlev değiştiricisi anahtar durumlar sürükleme işlemi sırasında denetlemenizi sağlar.|

## <a name="see-also"></a>Ayrıca Bkz.

[Sürükleme ve Bırakma (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropSource Sınıfı](../mfc/reference/coledropsource-class.md)<br/>
[COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
