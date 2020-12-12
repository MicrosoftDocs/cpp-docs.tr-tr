---
description: 'Daha fazla bilgi edinin: arabirimler (ATL)'
title: Arabirimler (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: d68f482d05ff828631f5f9f27085f24af188d643
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147699"
---
# <a name="interfaces-atl"></a>Arabirimler (ATL)

Bir arabirim, bir nesnenin işlevlerini dış dünyaya sunma yöntemidir. COM 'da arabirim, nesne tarafından uygulanan işlevlerde (C++ vtable gibi) işaretçiler tablosudur. Tablo, arabirimi ve işaret ettiği işlevleri, bu arabirimin yöntemleri temsil eder. Bir nesne seçtiği kadar çok sayıda arabirim sunabilir.

Her arabirim, [IUnknown](../atl/iunknown.md)temel com arabirimine dayalıdır. `IUnknown`Nesnesi tarafından kullanıma sunulan diğer arabirimlere gezinmeye izin verme yöntemleri.

Ayrıca, her arabirime benzersiz bir arabirim KIMLIĞI (IID) verilir. Bu benzersizlik, arabirim sürümü oluşturmayı desteklemeyi kolaylaştırır. Bir arabirimin yeni sürümü yeni bir IID ile yalnızca yeni bir arabirimdir.

> [!NOTE]
> Standart COM ve OLE arabirimleri için IIDS önceden tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[COM nesneleri ve arabirimleri](/windows/win32/com/com-objects-and-interfaces)
