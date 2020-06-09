---
title: Görüntü Listelerindeki Görüntü Bilgileri
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: c12198c769585763095d22b73d11f7af3c9d6fc0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624506"
---
# <a name="image-information-in-image-lists"></a>Görüntü Listelerindeki Görüntü Bilgileri

[CImageList](reference/cimagelist-class.md) , bir görüntü listesinden bilgi alan birkaç işlev içerir. [GetImageInfo](reference/cimagelist-class.md#getimageinfo) üye işlevi, `IMAGEINFO` görüntü ve maske bit eşlemlerinin tutamaçları, piksel başına renk düzlemleri ile bit sayısı ve görüntünün sınırlayıcı dikdörtgeni dahil olmak üzere tek bir görüntüyle ilgili bilgilerle bir yapıyı doldurur. Bu bilgileri, görüntünün bit eşlemlerini doğrudan işlemek için kullanabilirsiniz.

[GetImageCount](reference/cimagelist-class.md#getimagecount) üye işlevi, görüntü listesindeki görüntü sayısını alır.

[ExtractIcon](reference/cimagelist-class.md#extracticon) member işlevini kullanarak bir görüntü listesindeki bir görüntü ve maskeyi temel alan bir simge oluşturabilirsiniz. İşlevi, yeni simgenin tanıtıcısını döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](using-cimagelist.md)<br/>
[Denetimler](controls-mfc.md)
