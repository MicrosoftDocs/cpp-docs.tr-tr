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
ms.openlocfilehash: 687585d0b25c64f5575646de3cd4823e0a89988e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408992"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>CLR Kapatmasında /clr ile Oluşturulan COM Nesnelerini Tüketirken Özel Durumları Önleme

Ortak dil çalışma zamanı (CLR) kapatma girdikten sonra yerel işlevleri CLR hizmetlere erişimi sınırlı. Yayın çağırma girişimi sırasında bir COM nesnesi ile derlenmiş **/CLR**, CLR geçişleri için yerel kod ve geçişleri geri yönetilen koda hizmet (yönetilen kod içinde tanımlanmıştır) IUnknown::Release çağrısı. Kapatma modunda olduğundan CLR, yönetilen kod uygulamasına geri çağrı engeller.

Bu sorunu çözmek için yayın yöntemlerinden çağırılan yıkıcıların yalnızca yerel kod içeren emin olun.

## <a name="see-also"></a>Ayrıca Bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)