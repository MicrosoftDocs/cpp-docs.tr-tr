---
title: Satır İçi Derleme Avantajları
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
ms.openlocfilehash: ecf1598ec90a8600e1fa9aae565724c254dc11e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556747"
---
# <a name="advantages-of-inline-assembly"></a>Satır İçi Derleme Avantajları

**Microsoft'a özgü**

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. C veya C++ deyimleri ile satır içi derleme kodu karıştırılabilir olduğundan, onu kullanışsız ya da C veya C++ olanaksız olan görevleri yapabilirsiniz.

Satır içi derlemenin kullanımları şunlardır:

- Derleme dilinde işlevler yazma.

- Nokta iyileştirme hızı açısından kritik kod bölümlerini.

- Doğrudan donanım erişimi için cihaz sürücüleri yapılıyor.

- "Çıplak" çağrıları için prolog ve epilog kodu yazılıyor.

Satır içi derleme özel amaçlı bir araçtır. Bir uygulama farklı makinelere bağlantı noktası planlıyorsanız, makineye özgü kod içinde ayrı bir modül yerleştirmek isteyebilirsiniz. Satır içi assembler tüm Microsoft Macro Assembler's (MASM) desteklemediğinden makrosu ve veri yönergeleri bulduğunuz bunu daha kolay MASM böyle modüller için kullanılacak.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>