---
title: WINVER ve _WıN32_WıNNT güncelleştirme
ms.date: 09/04/2017
helpviewer_keywords:
- WINVER in an upgraded Visual Studio C++ project
- _WIN32_WINNT in an upgraded Visual Studio C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: 0cfdb3d065a85bd02ef21de9c4c5282cf54fcb2a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627251"
---
# <a name="update-winver-and-_win32_winnt"></a>WINVER ve _WıN32_WıNNT güncelleştirme

Görsel C++ artık Windows 95, Windows 98, Windows Me, Windows NT veya Windows 2000 'in hedeflenmesini desteklememektedir. Bu Windows sürümlerinden birine **WINVER** veya **_Wın32_wınnt** makrolarınızı atanırsa, makroları değiştirmeniz gerekir. Visual C++'ın önceki bir sürümü kullanılarak oluşturulmuş bir projeyi yükselttiğinizde, artık desteklenmeyen bir Windows sürümüne atandıklarında, **WINVER** veya **_WIN32_WINNT** makrolarıyla ilgili derleme hataları görebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Makroları değiştirmek için bir başlık dosyasında (örneğin, Windows 'u hedefleyen bir proje oluşturduğunuzda dahil olan targetver. h), aşağıdaki satırları ekleyin.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

Bu, Windows 10 işletim sistemini hedefler. Bu değerler, her bir Windows sürümü için makroları da tanımlayan SDKDDKVer. h Windows üst bilgi dosyasında listelenmiştir. SDKDDKVer. h öğesini eklemeden önce #define ifadesini eklemelisiniz. Aşağıda, SDKDDKVer. h 'nin Windows 'un her bir sürümünün değerlerini kodlayan Windows 10 sürümünün satırları verilmiştir:

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

Aradığınız SDKDDKVer. h kopyasında listelenen bu Windows sürümlerinin tümünü görmüyorsanız büyük olasılıkla Windows SDK eski bir sürümünü kullanıyorsunuz. Varsayılan olarak, Visual Studio 2017 ' de Win32 projeleri Windows 10 SDK 'sını kullanır.

> [!NOTE]
> Uygulamanıza iç MFC üstbilgileri eklerseniz, değerlerin çalışması garanti edilmez.

Ayrıca, bu makroyu `/D` derleyici seçeneğini kullanarak da tanımlayabilirsiniz. Daha fazla bilgi için bkz. [/d (Önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md).

Bu makroların anlamları hakkında daha fazla bilgi için bkz. [Windows üst bilgilerini kullanma](/windows/win32/WinProg/using-the-windows-headers).

## <a name="see-also"></a>Ayrıca bkz.

[Görsel C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)
