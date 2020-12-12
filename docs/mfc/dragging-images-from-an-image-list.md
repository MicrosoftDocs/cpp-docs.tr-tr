---
description: 'Daha fazla bilgi edinin: görüntü listesinden görüntü sürükleme'
title: Görüntü Listesinden Görüntü Sürükleme
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
ms.openlocfilehash: 4d81be73484d32d9b26e5aa4ae48b7e550306493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118855"
---
# <a name="dragging-images-from-an-image-list"></a>Görüntü Listesinden Görüntü Sürükleme

[CImageList](reference/cimagelist-class.md) , ekranda görüntü sürüklemeye yönelik işlevleri içerir. Sürükleme işlevleri bir görüntüyü düzgün bir şekilde, renkli ve imlecin herhangi bir yanıp sönmeksizin taşır. Hem maskelenmiş hem de maskelenmemiş görüntüler sürüklenebilir.

[BeginDrag](reference/cimagelist-class.md#begindrag) üye işlevi bir sürükleme işlemi başlatır. Parametreler, sürüklediğiniz görüntünün dizinini ve görüntünün içindeki etkin noktanın konumunu içerir. Etkin nokta, sürükleme işlevlerinin görüntünün tam ekran konumu olarak tanımadığı tek bir pikseldir. Genellikle, bir uygulama etkin noktayı fare imlecinin etkin noktası ile saatle çakışan olacak şekilde ayarlar. [DragMove](reference/cimagelist-class.md#dragmove) üye işlevi görüntüyü yeni bir konuma taşır.

[DragEnter](reference/cimagelist-class.md#dragenter) üye işlevi, sürükle resminin bir pencere içindeki ilk konumunu ayarlar ve görüntüyü konuma çizer. Parametreler, görüntünün çizildiği pencerenin bir işaretçisini ve penceredeki ilk konumun koordinatlarını belirten bir noktayı içerir. Koordinatlar, pencerenin sol üst köşesine göre değil, istemci alanına göre değil. Aynı değer, koordinatları parametre olarak alan tüm resim sürükleme işlevleri için de geçerlidir. Bu, koordinatları belirtirken kenarlık, başlık çubuğu ve menü çubuğu gibi pencere öğelerinin genişlikleri için telafi etmeniz gereken anlamına gelir. Çağrılırken **boş** bir pencere tutamacı belirtirseniz `DragEnter` , sürükleme işlevleri görüntüyü masaüstü penceresiyle ilişkili cihaz bağlamına çizer ve koordinatlar ekranın sol üst köşesine göre yapılır.

`DragEnter` sürükleme işlemi sırasında, diğer tüm güncelleştirmeleri verilen pencereye kilitler. Sürükleme işlemi sırasında bir sürükle ve bırak işleminin hedefini vurgulama gibi herhangi bir çizim yapmanız gerekiyorsa, [DragLeave](reference/cimagelist-class.md#dragleave) üye işlevini kullanarak sürüklenen görüntüyü geçici olarak gizleyebilirsiniz. Ayrıca, [DragShowNoLock](reference/cimagelist-class.md#dragshownolock) üye işlevini de kullanabilirsiniz.

Görüntüyü sürüklemeyi tamamladığınızda [EndDrag](reference/cimagelist-class.md#enddrag) çağrısı yapın.

[SetDragCursorImage](reference/cimagelist-class.md#setdragcursorimage) üye işlevi, belirtilen görüntüyü (genellikle bir fare imleç görüntüsünü) geçerli sürükleme görüntüsüyle birleştirerek yeni bir sürükleme görüntüsü oluşturur. Sürükleme işlevleri bir sürükleme işlemi sırasında yeni görüntüyü kullandığından, çağrıldıktan sonra asıl fare imlecini gizlemek için Windows [ShowCursor](/windows/win32/api/winuser/nf-winuser-showcursor) işlevini kullanmanız gerekir `SetDragCursorImage` . Aksi takdirde, sistem sürükleme işleminin süresi boyunca iki fare imleç gibi görünebilir.

Bir uygulama çağırdığında `BeginDrag` , sistem geçici, iç görüntü listesi oluşturur ve belirtilen sürükleme görüntüsünü iç listeye kopyalar. [Getdragimage](reference/cimagelist-class.md#getdragimage) üye işlevini kullanarak, geçici sürükleme resmi listesine bir işaretçi alabilirsiniz. İşlevi aynı zamanda sürükle konumuna göre sürükle ve sürükle konumunu alır.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](using-cimagelist.md)<br/>
[Denetimler](controls-mfc.md)
