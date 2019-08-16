---
title: Arabirimler (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 2373351330982623ffa602fd81bec61d0bc257b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492133"
---
# <a name="interfaces-atl"></a>Arabirimler (ATL)

Bir arabirim, bir nesnenin işlevlerini dış dünyaya sunma yöntemidir. COM 'da arabirim, nesne tarafından uygulanan işlevlerde işaretçiler ( C++ vtable gibi) tablosudur. Tablo, arabirimi ve işaret ettiği işlevleri, bu arabirimin yöntemleri temsil eder. Bir nesne seçtiği kadar çok sayıda arabirim sunabilir.

Her arabirim, [IUnknown](../atl/iunknown.md)temel com arabirimine dayalıdır. Nesnesi tarafından kullanıma `IUnknown` sunulan diğer arabirimlere gezinmeye izin verme yöntemleri.

Ayrıca, her arabirime benzersiz bir arabirim KIMLIĞI (IID) verilir. Bu benzersizlik, arabirim sürümü oluşturmayı desteklemeyi kolaylaştırır. Bir arabirimin yeni sürümü yeni bir IID ile yalnızca yeni bir arabirimdir.

> [!NOTE]
>  Standart COM ve OLE arabirimleri için IIDS önceden tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[COM nesneleri ve arabirimleri](/windows/win32/com/com-objects-and-interfaces)
