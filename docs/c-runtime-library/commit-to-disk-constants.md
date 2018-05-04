---
title: Commit-To-Disk sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- vc.constants
dev_langs:
- C++
helpviewer_keywords:
- commit-to-disk constants
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c3a815948c127c5dec0fe6412ab3c358aa409e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="commit-to-disk-constants"></a>Commit-To-Disk Sabitleri
**Microsoft özel**  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu Microsoft özgü sabitleri açık dosyayla ilişkili arabellek işletim sistemi arabelleklerini veya disk temizlenip temizlenmediğini belirtin. Mod okuma/yazma erişimi türünü belirleyen dizesine dahil (**"r"**, **"w"**, **"a"**, **"r +"**, **"w +"** , **"bir +"**).  
  
 Commit-to-disk modları aşağıdaki gibidir:  
  
 **c**  
 Belirtilen arabellek unwritten içeriğini diske yazar. Bu yürütme disk işlevi yalnızca açık çağrılar ya da ortaya [fflush](../c-runtime-library/reference/fflush.md) veya [_flushall](../c-runtime-library/reference/flushall.md) işlevi. Bu mod, hassas verilerle ilgilenirken kullanışlıdır. Örneğin, bir çağrı sonra programınızı sona ererse `fflush` veya `_flushall`, verilerinizi işletim sisteminin arabellekleri ulaşıldı emin olabilirsiniz. Ancak, bir dosya ile açılmış sürece **c** , veri hiçbir zaman Yap seçeneği, işletim sistemini de ererse diske.  
  
 **n**  
 Belirtilen arabellek unwritten içeriğini işletim sisteminin arabelleğe yazar. İşletim sistemi veriyi önbelleğe alma ve yazmak için bir en iyi zaman belirlemek için disk. Birçok koşullar altında bu davranış verimli program davranışını yapar. Ancak, veri saklama (banka hareketleri veya uçak bileti bilgi gibi) kritik öneme sahipse kullanmayı **c** seçeneği. **n** mod varsayılandır.  
  
> [!NOTE]
>  **c** ve **n** seçenekleri için standart ANSI parçası olmayan `fopen`, ancak Microsoft uzantıları ve burada ANSI taşınabilirlik istenen kullanılmamalıdır.  
  
## <a name="using-the-commit-to-disk-feature-with-existing-code"></a>Var olan kodda Commit-to-Disk özelliğini kullanma  
 Varsayılan olarak, çağrılar [fflush](../c-runtime-library/reference/fflush.md) veya [_flushall](../c-runtime-library/reference/flushall.md) kitaplık işlevleri işletim sistemi tarafından korunan arabellekleri için veri yazma. İşletim sistemi gerçekte diske veri yazmak için en iyi süreyi belirler. Çalışma Zamanı Kitaplığı commit-to-disk özellik kritik verileri doğrudan diske yerine işletim sisteminin arabellekleri için yazılmış emin olun olanak sağlar. Nesne dosyalarından COMMODE.OBJ ile bağlayarak yeniden olmadan, bu özellik için varolan bir programı verebilirsiniz.  
  
 Sonuçta elde edilen yürütülebilir dosyada çağrılar `fflush` doğrudan disk ve çağrıları arabellek içeriğini yazma `_flushall` tüm arabelleklerinin içeriğini diske yazma. Bu iki işlevler COMMODE.OBJ tarafından etkilenen yalnızca olanlardır.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../c-runtime-library/stream-i-o.md)   
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)