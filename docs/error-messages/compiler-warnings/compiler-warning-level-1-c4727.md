---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4727'
title: Derleyici Uyarısı (düzey 1) C4727
ms.date: 08/19/2019
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: 7639e6462cd5da0f5bd452bd0b80eddc80d5fe76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194117"
---
# <a name="compiler-warning-level-1-c4727"></a>Derleyici Uyarısı (düzey 1) C4727

"Obj_file_1 ve obj_file_2 aynı zaman damgasıyla birlikte PCH adlı pch_file.  İlk PCH 'yi kullanma.

> [!NOTE]
> Visual Studio 2017 ve önceki sürümlerde önceden derlenmiş üst bilgi, varsayılan olarak *stbafx. h* olarak adlandırılır ve visual Studio 2019 ve sonraki sürümlerinde, varsayılan olarak *pch. h* olarak adlandırılır.

C4727, **/Rivc** ile birden çok derleme derlenirken ve derleyicinin tüm. obj dosyalarını aynı. pch zaman damgasıyla işaretlebileceği durumlarda oluşur.

Çözümlemek için, **/Rivc/c** (pch oluşturur) ile bir kaynak dosya derleyin ve diğerleri **/Yu/c** (pch kullanır) ile ayrı olarak derleyin ve bunları birbirine bağlayın.

Bu nedenle, aşağıdakileri yaptıysanız ve C4727 oluşturursa:

::: moniker range="<=msvc-150"

**CL/clr/GL a. cpp b. cpp c. cpp/Ycstdafx.h**

Bunun yerine şunları yapabilirsiniz:

**CL/clr/GL a. cpp/Ycstdafx.h/c**

**CL/clr/GL b. cpp c. cpp/Yustdafx.h/link a. obj**

::: moniker-end

::: moniker range=">=msvc-160"

**CL/clr/GL a. cpp b. cpp c. cpp/Ycpch.h**

Bunun yerine şunları yapabilirsiniz:

**CL/clr/GL a. cpp/Ycpch.h/c**

**CL/clr/GL b. cpp c. cpp/Yupch.h/link a. obj**

::: moniker-end

Daha fazla bilgi için bkz.

- [/Yıc (ön derlenmiş üstbilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (önceden derlenmiş üst bilgi dosyasını kullan)](../../build/reference/yu-use-precompiled-header-file.md)
