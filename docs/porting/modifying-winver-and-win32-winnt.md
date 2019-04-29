---
title: WINVER ve _WIN32_WINNT'de Değişiklik Yapma
ms.date: 09/04/2017
helpviewer_keywords:
- WINVER in an upgraded Visual C++ project
- _WIN32_WINNT in an upgraded Visual C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: a936a54620590d4dc21f43acd50abdc49d77ffa8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337264"
---
# <a name="modifying-winver-and-win32winnt"></a>WINVER ve _WIN32_WINNT'de Değişiklik Yapma

Visual C++ artık hedefleme Windows 95, Windows 98, Windows ME, Windows NT veya Windows 2000 destekler. Varsa, **WINVER** veya **_WIN32_WINNT** makroları Windows'ın bu sürümlerinin birine atanır, makroları değiştirmeniz gerekir. Visual önceki bir sürümü kullanılarak oluşturulmuş bir projeyi yükselttiğinizde C++, derleme hatalarla ilgili **WINVER** veya **_WIN32_WINNT** bir sürüme atanmışsa makroları Windows, artık desteklenmiyor.

## <a name="remarks"></a>Açıklamalar

Makroları değiştirmek için (Windows hedefleyen bir proje oluşturduğunuzda, dahil olan örnek targetver.h), üstbilgi dosyasında aşağıdaki satırları ekleyin.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

Bu, Windows 10 işletim sistemini hedefler. Ayrıca her bir Windows sürümü için makroları tanımlayan SDKDDKVer.h Windows üstbilgi dosyasında bu değerleri listelenmektedir. Eklemeniz gerekir #define sdkddkver.h dosyasını eklemeden önce. SDKDDKVer.h Windows 10 sürümünden Windows her sürümü için değerleri kodlama satırları şunlardır:

```C
//
// _WIN32_WINNT version constants
//
#define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0
#define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000
#define _WIN32_WINNT_WINXP                  0x0501 // Windows XP
#define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003
#define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista
#define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista
#define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008
#define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista
#define _WIN32_WINNT_WIN7                   0x0601 // Windows 7
#define _WIN32_WINNT_WIN8                   0x0602 // Windows 8
#define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1
#define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10
#define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10
```

Bu Windows sürümlerinin tümünün bir kopyasını görüntülemekte olduğunuz SDKDDKVer.h listelenen görmüyorsanız, büyük olasılıkla Windows SDK'sı daha eski bir sürümünü kullanıyor. Varsayılan olarak, Win32 projeleri Visual Studio 2017'de Windows 10 SDK'sını kullanın.

> [!NOTE]
> Değerleri, uygulamanızda iç MFC üst bilgiler dahil ederseniz çalışmaya garanti edilmez.

Bu makroyu kullanarak da tanımlayabilirsiniz `/D` derleyici seçeneği. Daha fazla bilgi için [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md).

Bu makrolar anlamlara hakkında daha fazla bilgi için bkz. [Windows üst bilgileri kullanma](/windows/desktop/WinProg/using-the-windows-headers).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)
