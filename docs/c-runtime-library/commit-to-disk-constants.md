---
description: 'Daha fazla bilgi edinin: diske alma sabitleri'
title: Commit-To-Disk Sabitleri
ms.date: 11/04/2016
f1_keywords:
- vc.constants
helpviewer_keywords:
- commit-to-disk constants
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
ms.openlocfilehash: 416729f4b3b7bfdfdcb0ba11193f6c2a52691e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322653"
---
# <a name="commit-to-disk-constants"></a>Commit-To-Disk Sabitleri

**Microsoft'a Özgü**

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu Microsoft 'a özgü sabitler, Açık dosyayla ilişkili arabelleğin işletim sistemi arabelleklerine veya diske temizlenip temizlenmediğini belirtir. Mod, okuma/yazma erişimi türünü belirten dizeye dahildir (**"r"**, " **w"**, **"a"**, **"r +"**, **"w +"**, **"a +"**).

Diske kaydet modları aşağıdaki gibidir:

- **,**

   Belirtilen arabelleğin yazılı olmayan içeriğini diske yazar. Bu işlemi diske kaydet işlevi yalnızca [fflush](../c-runtime-library/reference/fflush.md) veya [_flushall](../c-runtime-library/reference/flushall.md) işlevine yönelik açık çağrılardan oluşur. Bu mod hassas verilerle ilgilenirken faydalıdır. Örneğin, programınız veya çağrısından sonra sonlandırılırsa `fflush` `_flushall` , verilerinizin işletim sisteminin arabelleklerine ulaştığından emin olabilirsiniz. Ancak, bir dosya **c** seçeneğiyle açılmadığı takdirde, işletim sistemi de sonlandığında veriler hiçbir şekilde diske yapmayabilir.

- **n**

   Belirtilen arabelleğin yazılı içeriğini işletim sisteminin arabelleklerine yazar. İşletim sistemi verileri önbelleğe alabilir ve ardından diske yazmak için en iyi zamanı belirleyebilir. Birçok koşulda, bu davranış etkin program davranışına olanak sağlar. Ancak, verilerin saklama süresi kritik ise (örneğin, banka işlemleri veya hava yolu bilet bilgileri) **c** seçeneğini kullanmayı düşünün. **N** modu varsayılandır.

> [!NOTE]
> **C** ve **n** seçenekleri için ANSI standardının bir parçası değildir `fopen` , ancak Microsoft uzantıları olur ve ANSI taşınabilirliği istendiği yerde kullanılmamalıdır.

## <a name="using-the-commit-to-disk-feature-with-existing-code"></a>Mevcut kodla diske kaydet özelliğini kullanma

Varsayılan olarak, [fflush](../c-runtime-library/reference/fflush.md) veya [_flushall](../c-runtime-library/reference/flushall.md) kitaplığı işlevlerine yapılan çağrılar, işletim sistemi tarafından tutulan arabelleklere veri yazar. İşletim sistemi, verileri diske gerçekten yazmak için en iyi zamanı belirler. Çalışma zamanı kitaplığının diske kaydet özelliği, kritik verilerin işletim sisteminin arabellekleri yerine doğrudan diske yazılmasını sağlamanıza olanak tanır. Bu özelliği, nesne dosyalarını COMMODE. OBJ ile bağlayarak mevcut bir programa yeniden yazmadan izin verebilirsiniz.

Elde edilen yürütülebilir dosyada, `fflush` arabelleğin içeriğini doğrudan diske yazmak için çağırır ve `_flushall` Tüm arabelleklerin içeriğini diske yazmak için çağırır. Bu iki işlev, COMMODE. OBJ tarafından etkilenen tek şeydir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
