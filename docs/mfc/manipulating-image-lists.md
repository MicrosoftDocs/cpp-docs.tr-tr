---
title: Görüntü listelerini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1eeccfa5245c6395e530859eb91c7f9a5c01335e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930377"
---
# <a name="manipulating-image-lists"></a>Görüntü Listelerini Düzenleme
[Değiştir](../mfc/reference/cimagelist-class.md#replace) üye işlevi bir resim listesi görüntüdeki değiştirir ([Cımagelist](../mfc/reference/cimagelist-class.md)) yeni bir görüntü ile. Bu işlev, ayrıca dinamik olarak bir resim listesi nesnesi görüntülerinde sayısını artırmak gerektiğinde kullanışlı olur. [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) işlevi görüntü listesinde depolanan görüntü sayısını dinamik olarak değişir. Resim listesi boyutunu artırmak için arama `Replace` yeni görüntü yuvalarına görüntüleri eklemek için. Görüntü listesi boyutu azaltırsanız, yeni boyutunu aşan görüntüleri kurtulurlar.  
  
 [Kaldırmak](../mfc/reference/cimagelist-class.md#remove) üye işlevi görüntü listesinden görüntü kaldırır. [Kopyalama](../mfc/reference/cimagelist-class.md#copy) üye işlevi kopyalayabilir veya takas bir resim listesi içinde görüntüler. Bu işlev kaynak görüntü hedef dizinine kopyalanmış olmalıdır ya da kaynak ve hedef görüntüleri takas belirtmenize olanak sağlar.  
  
 Görüntü listelerini birleştirerek yeni bir görüntü listesi oluşturmak için uygun aşırı yüklemesine kullanın [oluşturma](../mfc/reference/cimagelist-class.md#create) üye işlevi. Bu aşırı yüklemesini `Create` mevcut görüntü ilk görüntüsünü listeler, yeni bir görüntü listesi nesne sonuç görüntünün depolama birleştirme. Yeni görüntüyü ikinci resmin saydam ilk çizim tarafından oluşturulur. Yeni görüntüyü maskesini için var olan iki görüntü maskeleri BITS bir mantıksal OR işlemi gerçekleştirilirken sonucudur.  
  
 Tüm görüntüleri birleştirilmiş ve yeni görüntü Liste nesnesine eklendi kadar yinelenir.  
  
 Çağırarak arşive görüntü bilgileri yazabilirsiniz [yazma](../mfc/reference/cimagelist-class.md#write) üye işlevini ve geri çağırma okunur [okuma](../mfc/reference/cimagelist-class.md#read) üye işlevi.  
  
 [GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [Attach](../mfc/reference/cimagelist-class.md#attach), ve [ayırma](../mfc/reference/cimagelist-class.md#detach) üye işlevleri bağlı görüntü listesi tanıtıcısı değiştirmenize izin `CImageList` nesnesi sırada [DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) üye işlevi zarar vermeden resim listesi siler `CImageList` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cımagelist kullanma](../mfc/using-cimagelist.md)   
 [Denetimler](../mfc/controls-mfc.md)

