---
title: setjmp longjump
ms.date: 11/04/2016
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
ms.openlocfilehash: 765cef3f02bed09bed0278aaeecdcdbd55d86b67
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427904"
---
# <a name="setjmplongjump"></a>setjmp/longjump

Setjmpex.h veya setjmp.h eklediğinizde, tüm çağrılar [setjmp](../c-runtime-library/reference/setjmp.md) veya [longjmp](../c-runtime-library/reference/longjmp.md) yok ediciler çağırır ve son olarak çağıran bir bırakma neden olur.  Finally yan tümcelerinde setjmp.h sonuçları dahil olmak üzere burada ve Yıkıcılar değil çağrılan x86 farklıdır.

Bir çağrı `setjmp` geçerli yığın işaretçisi, geçici olmayan kayıtlar ve MxCsr kayıtları korur.  Çağrılar `longjmp` dönün en son `setjmp` site ve sıfırlar yığın işaretçisi, geçici olmayan kayıtlar ve MxCsr kaydeder, duruma göre en güncel korunduğu çağırmak `setjmp` çağırın.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)