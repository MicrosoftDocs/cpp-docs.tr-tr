---
description: 'Hakkında daha fazla bilgi edinin: genel pencere oluşturma sırası'
title: Genel Pencere Oluşturma Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 78a27114ebe3ac309ea8afdc6e04df65f1df1df8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189268"
---
# <a name="general-window-creation-sequence"></a>Genel Pencere Oluşturma Dizisi

Kendi oluşturduğunuz bir pencere oluşturduğunuzda (örneğin, alt pencere), çerçeve [belge/görünüm oluşturma](document-view-creation.md)bölümünde açıklananla çok daha fazla işlem kullanır.

MFC tarafından sunulan tüm pencere sınıfları [iki aşamalı oluşturma](one-stage-and-two-stage-construction-of-objects.md)gerçekleştirerek. Diğer bir deyişle, C++ işlecinin çağrılması sırasında **`new`** , Oluşturucu bir c++ nesnesini ayırır ve başlatır, ancak buna karşılık gelen bir Windows penceresi oluşturmaz. Bu, daha sonra pencere nesnesinin üye [Oluştur](reference/cwnd-class.md#create) işlevi çağırarak yapılır.

`Create`Üye Işlevi Windows penceresini yapar ve bunu `HWND` C++ nesnesinin ortak veri üyesi [m_hWnd](reference/cwnd-class.md#m_hwnd)depolar. `Create` oluşturma parametreleri üzerinde tüm esnekliği verir. `Create`' İ çağırmadan önce, çerçeveye ait simge ve sınıf stillerini ayarlamak Için [AfxRegisterWndClass](reference/application-information-and-management.md#afxregisterwndclass) genel işlevinde bir pencere sınıfını kaydetmek isteyebilirsiniz.

Çerçeve pencereleri için yerine [LoadFrame](reference/cframewnd-class.md#loadframe) üye işlevini kullanabilirsiniz `Create` . `LoadFrame` Windows penceresini daha az parametre kullanarak yapar. Bu, kaynakların başlık, simge, Hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardan birçok varsayılan değeri alır.

> [!NOTE]
> Simgenin, Hızlandırıcı tablonuzun ve menü kaynaklarınızın, **IDR_MAINFRAME** gibi ortak BIR kaynak kimliğine sahip olması gerekir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere nesneleri](window-objects.md)

- [Pencere "sınıfları" kaydediliyor](registering-window-classes.md)

- [Pencere nesnelerini yok etme](destroying-window-objects.md)

- [Belge çerçeve pencereleri oluşturma](creating-document-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows oluşturma](creating-windows.md)
