---
title: Arabirimler (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 3f6e8978c01d6689118a3a004c48e75a40151490
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594746"
---
# <a name="interfaces-atl"></a>Arabirimler (ATL)

Bir arabirim bir nesne dış dünya için işlevselliği kullanıma sunan bir yoludur. COM, bir arabirim işaretçileri nesne tarafından uygulanan işlevleri (örneğin, bir C++ vtable) bir tablodur. Tablo arabirimi temsil eder ve işaret ettiği işlevleri o arabirimin yöntemlerdir. Bir nesneyi seçer gibi çok arabirimleri kullanıma sunabilirsiniz.

Her arabirim temel COM arabirimi dayanır [IUnknown](../atl/iunknown.md). Yöntemlerinin `IUnknown` Gezinti nesne tarafından sunulan diğer arabirimler için izin verin.

Ayrıca, her bir arabirime benzersiz bir arabirim Kimliğini (IID) verilir. Bu benzersizlik arabirimi sürüm oluşturma desteği kolaylaştırır. Bir arabirim yeni bir sürümü yalnızca bir yeni, yeni bir IID ile arabirimidir.

> [!NOTE]
>  Standart COM ve OLE arabirimleri için IID'leri önceden tanımlanmıştır.

## <a name="see-also"></a>Ayrıca Bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[COM nesneleri ve arabirimler](/windows/desktop/com/com-objects-and-interfaces)

