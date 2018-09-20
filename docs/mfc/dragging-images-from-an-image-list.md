---
title: Görüntü listesinden görüntü sürükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb872cba298d6d18ab5287a285b22d2f568fa04b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382381"
---
# <a name="dragging-images-from-an-image-list"></a>Görüntü Listesinden Görüntü Sürükleme

[Cımagelist](../mfc/reference/cimagelist-class.md) ekranda bir görüntü sürükleme işlevleri içerir. Sürükleme işlevleri görüntünün sorunsuz, renk ve imlecin bulunduğu herhangi bir yanıp olmadan taşıyın. Maskeli ve maskelenmemiş görüntüleri sürüklenebilir.

[BeginDrag başarıyla](../mfc/reference/cimagelist-class.md#begindrag) üye işlevi bir sürükleme işlemi başlar. Parametreleri resme sürükleyin ve etkin nokta resim içindeki konumunu dizinini içerir. Etkin nokta sürükleyerek işlevleri görüntünün tam ekran konumunu tanıyacak tek bir piksel ' dir. Genellikle, uygulamanın etkin nokta ayarlar, böylece fare işaretçisinin etkin nokta ile örtüşür. [DragMove](../mfc/reference/cimagelist-class.md#dragmove) üye işlevi, görüntünün yeni bir konuma taşır.

[DragEnter](../mfc/reference/cimagelist-class.md#dragenter) üye işlevi bir pencere içinde görüntüyü Sürükle ilk konumunu ayarlar ve konumda resim çizer. Parametreleri, görüntü ve koordinatlarını penceresi bölgesindeki ilk konumunu belirten bir noktası çizmek penceresine bir işaretçi içerir. Pencerenin sol üst köşesindeki, istemci alanına göre koordinatlar belirlenir. Aynı tüm koordinatları parametre olarak alan görüntü sürükleme işlevleri için geçerlidir. Başka bir deyişle, kenarlık, başlık çubuğu ve menü çubuğu gibi Pencere öğelerinin genişlikleri koordinatları belirtirken dengelemek gerekir. Belirtirseniz bir **NULL** çağırırken pencere tanıtıcısı `DragEnter`sürükleyerek işlevleri masaüstü pencere ile ilgili cihaz bağlamı görüntü çizme ve ekranın sol üst köşesinde göreli koordinatları.

`DragEnter` sürükleme işlemi sırasında belirtilen pencereye diğer tüm güncelleştirmeleri kilitler. Bir Sürükle ve bırak işleminin hedef vurgulama gibi bir sürükleme işlemi sırasında herhangi bir çizim yapmanız gerekiyorsa, geçici olarak sürüklenen görüntüyü kullanarak gizleyebilirsiniz [DragLeave](../mfc/reference/cimagelist-class.md#dragleave) üye işlevi. Ayrıca [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock) üye işlevi.

Çağrı [EndDrag](../mfc/reference/cimagelist-class.md#enddrag) bitirdiğinizde görüntüyü sürükleyerek.

[SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage) üye işlevi, belirtilen görüntünün (genellikle bir fare imleci görüntüsü) ile geçerli görüntüyü Sürükle birleştirerek yeni bir görüntüyü Sürükle oluşturur. Sürükleme işlevleri bir sürükleme işlemi sırasında yeni görüntüyü kullandığından, Windows kullanması gereken [sayı değil geçiş](/windows/desktop/api/winuser/nf-winuser-showcursor) işlevi çağırdıktan sonra gerçek fare imleci gizlemek için `SetDragCursorImage`. Aksi takdirde, sistem sürükleme işlemi süresince iki fare imleçleri sahip görünebilir.

Bir uygulama çağırdığında `BeginDrag`, sistemin geçici, iç görüntü listesi oluşturur ve kopya belirtilen görüntü iç listesine sürükleyin. Geçici Sürükle resim listesi için bir işaretçi kullanarak alabilirsiniz [GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage) üye işlevi. İşlev ayrıca geçerli Sürükle konumu ve görüntüyü Sürükle Sürükle konumuna göre uzaklığı alır.

## <a name="see-also"></a>Ayrıca Bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

