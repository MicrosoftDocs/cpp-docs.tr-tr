---
description: 'Hakkında daha fazla bilgi edinin: üstbilgi denetimindeki öğeleri sıralama'
title: Üstbilgi Denetimindeki Öğeleri Sıralama
ms.date: 11/04/2016
f1_keywords:
- DS_DRAGDROP
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
ms.openlocfilehash: 6f6db7b134121c4084d9406ad537bf0ce5dc12cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330117"
---
# <a name="ordering-items-in-the-header-control"></a>Üstbilgi Denetimindeki Öğeleri Sıralama

[Bir üst bilgi denetimine öğe ekledikten](adding-items-to-the-header-control.md)sonra, aşağıdaki işlevlerle sırasıyla sırası hakkında bilgi alabilirsiniz:

- [CHeaderCtrl:: GetOrderArray](reference/cheaderctrl-class.md#getorderarray) ve [CHeaderCtrl:: SetOrderArray](reference/cheaderctrl-class.md#setorderarray)

   Üst bilgi öğelerinin soldan sağa sırasını alır ve ayarlar.

- [CHeaderCtrl:: Ordertoındex](reference/cheaderctrl-class.md#ordertoindex).

   Belirli bir üst bilgi öğesi için dizin değerini alır.

Önceki üye işlevlerine ek olarak, HDS_DRAGDROP stili kullanıcının üst bilgi denetimi içinde üst bilgi öğelerini sürükleyip bırakması için izin verir. Daha fazla bilgi için bkz. [üst bilgi öğeleri Için sürükle ve bırak desteği sağlama](providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](using-cheaderctrl.md)
