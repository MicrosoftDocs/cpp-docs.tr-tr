---
title: Derleyici Uyarısı (düzey 1) C4727
ms.date: 08/19/2019
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: 6b0ca74bbd03682f91206c21c3413d4ad168b60a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185873"
---
# <a name="compiler-warning-level-1-c4727"></a>Derleyici Uyarısı (düzey 1) C4727

"Obj_file_1 ve obj_file_2 aynı zaman damgasıyla birlikte PCH adlı pch_file.  İlk PCH 'yi kullanma.

> [!NOTE]
> Visual Studio 2017 ve önceki sürümlerde önceden derlenmiş üst bilgi, varsayılan olarak *stbafx. h* olarak adlandırılır ve visual Studio 2019 ve sonraki sürümlerinde, varsayılan olarak *pch. h* olarak adlandırılır.

C4727, **/Rivc**ile birden çok derleme derlenirken ve derleyicinin tüm. obj dosyalarını aynı. pch zaman damgasıyla işaretlebileceği durumlarda oluşur.

Çözümlemek için, **/Rivc/c** (pch oluşturur) ile bir kaynak dosya derleyin ve diğerleri **/Yu/c** (pch kullanır) ile ayrı olarak derleyin ve bunları birbirine bağlayın.

Bu nedenle, aşağıdakileri yaptıysanız ve C4727 oluşturursa:

::: moniker range="<=vs-2017"

**CL/clr/GL a. cpp b. cpp c. cpp/Ycstdafx.h**

Bunun yerine şunları yapabilirsiniz:

**CL/clr/GL a. cpp/Ycstdafx.h/c**

**CL/clr/GL b. cpp c. cpp/Yustdafx.h/link a. obj**

::: moniker-end

::: moniker range=">=vs-2019"

**CL/clr/GL a. cpp b. cpp c. cpp/Ycpch.h**

Bunun yerine şunları yapabilirsiniz:

**CL/clr/GL a. cpp/Ycpch.h/c**

**CL/clr/GL b. cpp c. cpp/Yupch.h/link a. obj**

::: moniker-end

Daha fazla bilgi için bkz.

- [/Yc (Önceden Derlenmiş Üst Bilgi Dosyası Oluştur)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (Önceden Derlenmiş Üst Bilgi Dosyasını Kullanma)](../../build/reference/yu-use-precompiled-header-file.md)
