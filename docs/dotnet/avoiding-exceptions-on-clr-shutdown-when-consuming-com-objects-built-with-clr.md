---
title: -Clr ile oluşturulan COM nesnelerini tarafından oluşturulan özel durumları önleme
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: bafcfb4e8a8abfecc8491220202b63971bef1ac8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393837"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>CLR Kapatmasında /clr ile Oluşturulan COM Nesnelerini Tüketirken Özel Durumları Önleme

Ortak dil çalışma zamanı (CLR) kapatma girdikten sonra yerel işlevleri CLR hizmetlere erişimi sınırlı. Yayın çağırma girişimi sırasında bir COM nesnesi ile derlenmiş **/CLR**, CLR geçişleri için yerel kod ve geçişleri geri yönetilen koda hizmet (yönetilen kod içinde tanımlanmıştır) IUnknown::Release çağrısı. Kapatma modunda olduğundan CLR, yönetilen kod uygulamasına geri çağrı engeller.

Bu sorunu çözmek için yayın yöntemlerinden çağırılan yıkıcıların yalnızca yerel kod içeren emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
