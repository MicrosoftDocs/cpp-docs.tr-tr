---
title: sinyal Eylemi Sabitleri
ms.date: 11/04/2016
f1_keywords:
- SIG_IGN
- SIG_DFL
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
ms.openlocfilehash: a7448730501d6f3b50008966134f708ae99ddb5b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830767"
---
# <a name="signal-action-constants"></a>sinyal Eylemi Sabitleri

Kesme sinyali alındığında gerçekleştirilecek eylem değerine bağlıdır `func` .

## <a name="syntax"></a>Syntax

```
#include <signal.h>
```

## <a name="remarks"></a>Açıklamalar

`func`Bağımsız değişken, bir işlev adresi veya aşağıda listelenen bildirim sabitlerinden biri veya sinyal içinde tanımlanmış olmalıdır. Olsun.

|Sabit|Açıklama|
|-|-|
| `SIG_DFL`  | Varsayılan sistem yanıtını kullanır. Çağıran program akış g/ç kullanıyorsa, çalışma zamanı kitaplığı tarafından oluşturulan arabellekler boşaltılmaz.  |
| `SIG_IGN`  | Kesme sinyalini yoksayar. İşlemin kayan nokta durumu tanımsız olduğundan, bu değer hiçbir şekilde verilmemelidir `SIGFPE` .  |
| `SIG_SGE`  | Sinyalde bir hata oluştuğunu gösterir.  |
| `SIG_ACK`  | Bir onay alındığını gösterir.  |
| `SIG_ERR`  | Bir hatayı gösteren bir sinyalin dönüş türü oluştu.  |

## <a name="see-also"></a>Ayrıca bkz.

[sinyal](../c-runtime-library/reference/signal.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
