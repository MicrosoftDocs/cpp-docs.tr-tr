---
title: "-Clr ile oluşturulan COM nesnelerini tarafından oluşturulan özel durumları önleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 287c9831f8c604272b37ac85528d66fe640de557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>CLR Kapatmasında /clr ile Oluşturulan COM Nesnelerini Tüketirken Özel Durumları Önleme
Ortak dil çalışma zamanı (CLR) kapatma moduna girdikten sonra yerel işlevler CLR hizmetlerine erişiminiz sınırlanır. Yayın çağırmak girişimi sırasında bir COM nesnesi ile derlenmiş **/CLR**, CLR geçişler için yerel kod ve geçişleri geri (yönetilen kodda tanımlanır) IUnknown::Release çağrısını hizmet vermek için yönetilen koda. CLR kapatma modunda olduğundan geri yönetilen koda çağrı engeller.  
  
 Bu sorunu çözmek için yayın yöntemlerinden çağırılan yıkıcıların yalnızca yerel kodu içeren emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)