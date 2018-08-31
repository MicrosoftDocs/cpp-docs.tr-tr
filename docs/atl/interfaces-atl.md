---
title: Arabirimler (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1410a437d87b56b244eb4fcd711797c279bec446
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217889"
---
# <a name="interfaces-atl"></a>Arabirimler (ATL)
Bir arabirim bir nesne dış dünya için işlevselliği kullanıma sunan bir yoludur. COM, bir arabirim işaretçileri nesne tarafından uygulanan işlevleri (örneğin, bir C++ vtable) bir tablodur. Tablo arabirimi temsil eder ve işaret ettiği işlevleri o arabirimin yöntemlerdir. Bir nesneyi seçer gibi çok arabirimleri kullanıma sunabilirsiniz.  
  
 Her arabirim temel COM arabirimi dayanır [IUnknown](../atl/iunknown.md). Yöntemlerinin `IUnknown` Gezinti nesne tarafından sunulan diğer arabirimler için izin verin.  
  
 Ayrıca, her bir arabirime benzersiz bir arabirim Kimliğini (IID) verilir. Bu benzersizlik arabirimi sürüm oluşturma desteği kolaylaştırır. Bir arabirim yeni bir sürümü yalnızca bir yeni, yeni bir IID ile arabirimidir.  
  
> [!NOTE]
>  Standart COM ve OLE arabirimleri için IID'leri önceden tanımlanmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM'a giriş](../atl/introduction-to-com.md)   
 [COM nesneleri ve arabirimler](/windows/desktop/com/com-objects-and-interfaces)

