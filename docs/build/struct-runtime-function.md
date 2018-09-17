---
title: RUNTIME_FUNCTION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f3831dc36664c556cf0a020ed87c60200443fd3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718243"
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