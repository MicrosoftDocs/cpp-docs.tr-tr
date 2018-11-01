---
title: Commit-To-Disk Sabitleri
ms.date: 11/04/2016
f1_keywords:
- vc.constants
helpviewer_keywords:
- commit-to-disk constants
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
ms.openlocfilehash: f4da66c913cd8a046257158e837e5bdb20ed71c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581408"
---
# <a name="commit-to-disk-constants"></a>Commit-To-Disk Sabitleri

**Microsoft'a özgü**

## <a name="syntax"></a>Sözdizimi

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu Microsoft'a özgü sabiti, açık dosya ile ilgili arabellek işletim sistemi arabelleklerini veya disk temizlenmediğini belirtin. Okuma/yazma erişimi türünü belirleyen dizesinde modu dahildir (**"r"**, **"w"**, **"a"**, **"r +"**, **"w +"** , **"a +"**).

Yürütme disk modları aşağıdaki gibidir:

- **c**

   Belirtilen arabellek yazılı içeriğini diske yazar. Bu işleme disk işlevi yalnızca ya da yapılan açık çağrıları ortaya [fflush](../c-runtime-library/reference/fflush.md) veya [_flushall](../c-runtime-library/reference/flushall.md) işlevi. Bu mod, hassas verilerle ilgilenirken kullanışlıdır. Örneğin, programınız çağrısı yapıldıktan sonra sona ererse `fflush` veya `_flushall`, verilerinizi işletim sisteminin arabellekler ulaştığını emin olabilirsiniz. Ancak, bir dosya ile açılmadıkça **c** seçeneği, veri hiçbir zaman kılmaktadır diske işletim sistemi de sonlandırır.

- **n**

   Belirtilen arabellek yazılı içeriğini işletim sisteminin arabelleğe yazar. İşletim sistemi, veriyi önbelleğe alma ve sonra yazmak için bir en iyi zamanı belirler diske. Birçok koşullar altında bu davranışı verimli program davranışını sağlar. Ancak, veri saklama (banka işlemleri veya uçak bileti bilgi gibi) önemliyse kullanmayı **c** seçeneği. **n** mod varsayılandır.

> [!NOTE]
> **c** ve **n** seçenekleri için standart ANSI parçası olmayan `fopen`, ancak Microsoft uzantılarıdır ve ANSI taşınabilirliğinin istendiği durumlarda kullanılmamalıdır.

## <a name="using-the-commit-to-disk-feature-with-existing-code"></a>Yürütme Disk özelliği mevcut kodu ile kullanma

Varsayılan olarak, çağrılar [fflush](../c-runtime-library/reference/fflush.md) veya [_flushall](../c-runtime-library/reference/flushall.md) kitaplık işlevleri için işletim sistemi tarafından korunan arabellekler veri yazma. İşletim sistemi, gerçekten verileri diske yazmak için en iyi zamanı belirler. Çalışma zamanı kitaplığının işleme disk özellik kritik verileri doğrudan disk yerine işletim sisteminin arabellekler yazıldığından emin olanak sağlar. Nesne dosyalarını COMMODE.OBJ ile bağlayarak yeniden olmadan, bu özellik için varolan bir program verebilirsiniz.

Oluşturulan yürütülebilir dosya olarak çağrılar `fflush` doğrudan disk ve çağrıları arabellek içeriğini yazma `_flushall` arabelleklerin içeriğini diske yazma. Bu iki işlevler COMMODE.OBJ tarafından etkilenen yalnızca olanlardır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Stream g/ç](../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
