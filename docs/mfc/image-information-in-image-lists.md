---
title: Görüntü listelerindeki görüntü bilgileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c98bc629cde74cf7a6fc8a416de862f50a1dd5ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422291"
---
# <a name="image-information-in-image-lists"></a>Görüntü Listelerindeki Görüntü Bilgileri

[Cımagelist](../mfc/reference/cimagelist-class.md) bilgi görüntü listesinden görüntü alma işlevleri içerir. [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) üye işlevi dolduran bir `IMAGEINFO` tutamaçları görüntü ve maskesi bit eşlemler, renk düzlemleri ve piksel başına bit sayısı ve dikdörtgen gibi tek bir görüntü ilgili bilgilerle yapısı Görüntü bit eşlem içinde bir görüntüsü. Bu bilgiler, bit eşlemler görüntüsü için doğrudan yönetmek için kullanabilirsiniz.

[Getımagecount](../mfc/reference/cimagelist-class.md#getimagecount) üye işlevi bir görüntü listesinden görüntü sayısını alır.

Bir simge kullanarak bir görüntü ve resim listesi maskesi göre oluşturabilirsiniz [ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) üye işlevi. İşlev, yeni simgesine tanıtıcısını döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

