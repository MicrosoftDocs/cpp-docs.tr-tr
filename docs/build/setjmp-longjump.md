---
title: setjmp longjump | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f53160a5deeb3ea0db111fc0aae7429b19b7cc86
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703280"
---
# <a name="setjmplongjump"></a>setjmp/longjump

Setjmpex.h veya setjmp.h eklediğinizde, tüm çağrılar [setjmp](../c-runtime-library/reference/setjmp.md) veya [longjmp](../c-runtime-library/reference/longjmp.md) yok ediciler çağırır ve son olarak çağıran bir bırakma neden olur.  Finally yan tümcelerinde setjmp.h sonuçları dahil olmak üzere burada ve Yıkıcılar değil çağrılan x86 farklıdır.

Bir çağrı `setjmp` geçerli yığın işaretçisi, geçici olmayan kayıtlar ve MxCsr kayıtları korur.  Çağrılar `longjmp` dönün en son `setjmp` site ve sıfırlar yığın işaretçisi, geçici olmayan kayıtlar ve MxCsr kaydeder, duruma göre en güncel korunduğu çağırmak `setjmp` çağırın.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)