---
title: Windows platformları (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility [C++], C run-time libraries
- compatibility [C++], C run-time libraries
- MBCS [C++], Win32 platforms
- operating systems [C++]
- Unicode [C++], Win32 platforms
ms.assetid: 0aacaf45-6dc4-4908-bd52-57abac7b39f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d53e8020bbb7649d78232025ef9c63c1dc868fee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="windows-platforms-crt"></a>Windows Platformları (CRT)

Visual Studio için C çalışma zamanı kitaplıkları geçerli Windows ve Windows Server sürümleri desteği [!INCLUDE[win8](../build/reference/includes/win8_md.md)], [!INCLUDE[winserver8](../build/reference/includes/winserver8_md.md)], [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/reference/includes/winsvr08_md.md)]ve Windows Vista ve isteğe bağlı destek [!INCLUDE[winxp](../build/includes/winxp_md.md)] x86, Service Pack 3 (SP3) [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 (SP2) x64, ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 (SP2) hem x86 hem x64. Tüm bu işletim sistemlerinin Windows Masaüstü API (Win32) destekler ve Unicode desteği sağlar. Ayrıca, herhangi bir Win32 uygulaması birden çok baytlı karakter kümesi (MBCS) kullanabilirsiniz.

> [!NOTE]
> Varsayılan yüklemesini **C++ ile masaüstü geliştirme** Visual Studio 2017 iş yükü için destek içermez [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] geliştirme. İsteğe bağlı bileşen yüklemeniz gerekir **C++ Windows XP desteği** bir Windows XP platform araç takımı etkinleştirmek için.

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)  
