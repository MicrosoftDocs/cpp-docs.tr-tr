---
description: 'Daha fazla bilgi için: görüntü listelerindeki görüntü bilgileri'
title: Görüntü Listelerindeki Görüntü Bilgileri
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: c3a5f1cee0a06177d12b72673bf0ebf8e1a73933
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290147"
---
# <a name="image-information-in-image-lists"></a>Görüntü Listelerindeki Görüntü Bilgileri

[CImageList](reference/cimagelist-class.md) , bir görüntü listesinden bilgi alan birkaç işlev içerir. [GetImageInfo](reference/cimagelist-class.md#getimageinfo) üye işlevi, `IMAGEINFO` görüntü ve maske bit eşlemlerinin tutamaçları, piksel başına renk düzlemleri ile bit sayısı ve görüntünün sınırlayıcı dikdörtgeni dahil olmak üzere tek bir görüntüyle ilgili bilgilerle bir yapıyı doldurur. Bu bilgileri, görüntünün bit eşlemlerini doğrudan işlemek için kullanabilirsiniz.

[GetImageCount](reference/cimagelist-class.md#getimagecount) üye işlevi, görüntü listesindeki görüntü sayısını alır.

[ExtractIcon](reference/cimagelist-class.md#extracticon) member işlevini kullanarak bir görüntü listesindeki bir görüntü ve maskeyi temel alan bir simge oluşturabilirsiniz. İşlevi, yeni simgenin tanıtıcısını döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](using-cimagelist.md)<br/>
[Denetimler](controls-mfc.md)
