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
ms.openlocfilehash: 0db5a79f187cb0fe320bf67aace751a5d4c537d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="interfaces-atl"></a>Arabirimler (ATL)
Arabirim bir nesne dış dünyaya işlevselliği kullanıma sunan yoludur. COM'da, bir nesne tarafından uygulanan işlev işaretçileri (C++ vtable gibi) bir tablonun arabirimdir. Tablo arabirimi temsil eder ve işaret ettiği işlevleri arabirimi yöntemleridir. Bir nesne seçtiği gibi sayıda arabirimleri getirebilir.  
  
 Her arabirimin temel COM arabirimi tabanlı [IUnknown](../atl/iunknown.md). Yöntemlerinin **IUnknown** Gezinti nesne tarafından kullanıma sunulan diğer arabirimlerine izin verin.  
  
 Ayrıca, her bir arabirime benzersiz arabirimi Kimliği'ni (IID) sağlanır. Bu benzersizlik arabirimi sürüm desteklemeyi kolaylaştırır. Arabirim yeni bir sürümü yalnızca bir yeni, yeni IID ile arabirimidir.  
  
> [!NOTE]
>  Standart COM ve OLE arabirimleri için IID'leri önceden tanımlanmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [COM nesneleri ve arabirimleri](http://msdn.microsoft.com/library/windows/desktop/ms690343)

