---
title: VarArgs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8305eaddf87a2e67b797bedff1944dbcbbbdbd41
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713654"
---
# <a name="varargs"></a>Varargs

Parametreler (örneğin, üç nokta bağımsız değişkenler) varargs geçirilir, temelde normal parametre geçirme beşinci ve sonraki bağımsız değişkenlere dahil olmak üzere uygulanır. Bunu yeniden çağrıyı yapanın adresleri alınıp döküm bağımsız değişkenlere sorumluluğundadır. Aranan değer tamsayı kayıtlara bekliyor durumunda yalnızca kayan nokta değerleri için float değeri hem tamsayı ve kayan nokta kaydı içerir.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)