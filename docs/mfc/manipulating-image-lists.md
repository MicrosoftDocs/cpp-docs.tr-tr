---
description: 'Daha fazla bilgi edinin: görüntü listelerini düzenleme'
title: Resim Listelerini Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
ms.openlocfilehash: dc2b136e1aed5266ea7cc910cf10839f59dfcf00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281138"
---
# <a name="manipulating-image-lists"></a>Resim Listelerini Düzenleme

[Değiştirme](reference/cimagelist-class.md#replace) üyesi işlevi bir görüntü listesindeki görüntünün ([CImageList](reference/cimagelist-class.md)) yeni bir görüntüyle yerini alır. Bu işlev, bir görüntü listesi nesnesindeki görüntü sayısını dinamik olarak artırmanız gerekiyorsa de kullanışlıdır. [SetImageCount](reference/cimagelist-class.md#setimagecount) işlevi, görüntü listesinde depolanan görüntü sayısını dinamik olarak değiştirir. Görüntü listesinin boyutunu artırdıysanız, `Replace` yeni görüntü yuvalarına görüntü ekleme ' yi çağırın. Görüntü listesinin boyutunu azaltırsanız, yeni boyuttan daha fazla görüntü serbest bırakılır.

[Remove](reference/cimagelist-class.md#remove) member işlevi bir görüntüyü görüntü listesinden kaldırır. [Kopya](reference/cimagelist-class.md#copy) üye işlevi bir görüntü listesi içindeki görüntüleri kopyalayabilir veya değiştirebilir. Bu işlev, kaynak görüntünün hedef dizine kopyalanıp kopyalanmayacağını belirtmenize veya kaynak ve hedef görüntülerin değiştirilip değiştirilmelidir.

İki resim listesini birleştirerek yeni bir görüntü listesi oluşturmak için, [Create](reference/cimagelist-class.md#create) member işlevinin uygun aşırı yüklemesini kullanın. ' Nin bu aşırı yüklemesi `Create` , sonuçta elde edilen görüntüyü yeni bir görüntü listesi nesnesinde depolayarak var olan görüntü listelerinin ilk görüntüsünü birleştirir. Yeni görüntü, ikinci resim saydam olarak ilk üzerine çizerek oluşturulur. Yeni görüntü için maske, var olan iki görüntünün maske bitleri üzerinde mantıksal veya bir işlem gerçekleştirme sonucudur.

Bu, tüm görüntüler birleştirilene ve yeni görüntü listesi nesnesine eklenene kadar yinelenir.

Görüntü bilgilerini, [yazma](reference/cimagelist-class.md#write) üyesi işlevini çağırarak bir arşive yazabilir ve [Oku](reference/cimagelist-class.md#read) üye işlevini çağırarak geri okuyabilirsiniz.

[GetSafeHandle](reference/cimagelist-class.md#getsafehandle), [Attach](reference/cimagelist-class.md#attach)ve [Detach](reference/cimagelist-class.md#detach) üye işlevleri, nesnesine eklenen görüntü listesinin tanıtıcısını değiştirmenize izin verir `CImageList` , ancak [DeleteImageList](reference/cimagelist-class.md#deleteimagelist) üye işlevi nesneyi yok etmek zorunda kalmadan görüntü listesini siler `CImageList` .

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](using-cimagelist.md)<br/>
[Denetimler](controls-mfc.md)
