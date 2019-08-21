---
title: Derleyici Uyarısı (düzey 1) C4727
ms.date: 08/19/2019
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: 1bcc029536d2602d50178d7148332b8371db3c7f
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630825"
---
# <a name="compiler-warning-level-1-c4727"></a>Derleyici Uyarısı (düzey 1) C4727

"Pch_file adlı PCH, obj_file_1 ve obj_file_2 içinde aynı zaman damgasıyla bulundu.  İlk PCH 'yi kullanma.

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