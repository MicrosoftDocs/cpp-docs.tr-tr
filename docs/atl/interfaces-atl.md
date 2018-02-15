---
title: Arabirimler (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 95dce7d707cfb29c8f33f94504c26b5b24ef4c4f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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

