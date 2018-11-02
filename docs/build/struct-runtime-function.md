---
title: struct RUNTIME_FUNCTION
ms.date: 11/04/2016
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
ms.openlocfilehash: 6b113f6cf1e9951f9e4578e15c9ed0af3d036fa6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520256"
---
# <a name="struct-runtimefunction"></a>struct RUNTIME_FUNCTION

Tablo tabanlı özel durum işleme, yığın alanı tahsis edin ya da başka bir işlevi (örneğin, yapraksız işlevler) tüm işlevler için bir tablo girişi gerektirir. İşlev tablo girişleri biçime sahiptir:

|||
|-|-|
|ULONG|Başlangıç adresi işlevi|
|ULONG|Bitiş adresi işlevi|
|ULONG|Bırakma bilgisi adresi|

RUNTIME_FUNCTION yapısını bellekte DWORD hizalanmış olmalıdır. Görüntü göreli tüm adreslerin, diğer bir deyişle, 32-bit uzaklıkları görüntünün işlevi tablo girişi içeren başlangıç adresinden oldukları. Bu girişler sıralanır ve je typu PE32 + görüntü .pdata bölümünde yerleştirin. [JIT derleyicileri] dinamik olarak üretilen işlevler için bu işlevleri desteklemek için çalışma zamanı ya da RtlInstallFunctionTableCallback ya da RtlAddFunctionTable işletim sistemi için bu bilgiyi sağlamak için kullanmanız gerekir. Bunun yapılmaması, işleme ve işlemlerde hata ayıklamanın güvenilir özel durumu oluşur.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme için Veri Bırakma, Hata Ayıklayıcı Desteği](../build/unwind-data-for-exception-handling-debugger-support.md)