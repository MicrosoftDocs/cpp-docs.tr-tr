---
title: Arabirimler (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 56d5a010bc28257dce181ee33e0ddf74655ccd3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319383"
---
# <a name="interfaces-atl"></a>Arabirimler (ATL)

Arabirim, bir nesnenin işlevselliğini dış dünyaya nasıl ortaya çıkarır? COM'da arabirim, nesne tarafından uygulanan işlevlere işaretçiler tablosudur (C++ vtable gibi). Tablo arabirimi temsil eder ve işaret ettiği işlevler bu arabirimin yöntemleridir. Bir nesne istediği kadar arabirim ortaya çıkarabilir.

Her arabirim temel COM arabirimi, [IUnknown](../atl/iunknown.md)dayanmaktadır. Nesne tarafından `IUnknown` maruz kalan diğer arabirimlere gezinmeye izin verme yöntemleri.

Ayrıca, her arabirim benzersiz bir arabirim kimliği (IID) verilir. Bu benzersizlik, arabirim sürümünü desteklemeyi kolaylaştırır. Arabirimin yeni bir sürümü, yeni bir IID ile sadece yeni bir arayüz.

> [!NOTE]
> Standart COM ve OLE arabirimleri için iID'ler önceden tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[COM Nesneleri ve Arayüzleri](/windows/win32/com/com-objects-and-interfaces)
