---
title: -Clr ile oluşturulan COM nesnelerini tarafından oluşturulan özel durumları önleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0efd2af7eb4bf8a70bff983d627f802f1976c6ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103518"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>CLR Kapatmasında /clr ile Oluşturulan COM Nesnelerini Tüketirken Özel Durumları Önleme
Ortak dil çalışma zamanı (CLR) kapatma moduna girdikten sonra yerel işlevler CLR hizmetlerine erişiminiz sınırlanır. Yayın çağırmak girişimi sırasında bir COM nesnesi ile derlenmiş **/CLR**, CLR geçişler için yerel kod ve geçişleri geri (yönetilen kodda tanımlanır) IUnknown::Release çağrısını hizmet vermek için yönetilen koda. CLR kapatma modunda olduğundan geri yönetilen koda çağrı engeller.  
  
 Bu sorunu çözmek için yayın yöntemlerinden çağırılan yıkıcıların yalnızca yerel kodu içeren emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)