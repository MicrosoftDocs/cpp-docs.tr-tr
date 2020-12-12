---
description: 'Daha fazla bilgi edinin: sinyal eylemi sabitleri'
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
ms.openlocfilehash: 380fed21b097b674958c6e2aae2f6b8c53845943
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276991"
---
# <a name="signal-action-constants"></a>sinyal Eylemi Sabitleri

Kesme sinyali alındığında gerçekleştirilecek eylem değerine bağlıdır `func` .

## <a name="syntax"></a>Syntax

```
#include <signal.h>
```

## <a name="remarks"></a>Açıklamalar

`func`Bağımsız değişken, bir işlev adresi veya aşağıda listelenen bildirim sabitlerinden biri veya SIGNAL. H içinde tanımlanmış olmalıdır.

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
