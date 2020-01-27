---
title: WINVER ve _WIN32_WINNT güncelleştirmesi
description: Yükseltilen Visual Studio C++ projelerindeki WINVER ve _WIN32_WINNT makrolarını güncelleştirme ve güncelleştirme.
ms.date: 01/22/2020
helpviewer_keywords:
- WINVER in an upgraded Visual Studio C++ project
- _WIN32_WINNT in an upgraded Visual Studio C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: b81c7967732c7b0c23ff0eb73d2a866a9b33713b
ms.sourcegitcommit: b67b08472b6f1ee8f1c5684bba7056d3e0fc745f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76725702"
---
# <a name="update-winver-and-_win32_winnt"></a>WINVER ve _WIN32_WINNT güncelleştirmesi

Windows SDK kullandığınızda, kodunuzun hangi Windows sürümlerini çalıştırabileceği belirtebilirsiniz. Önişlemci makroları **WINVER** ve **_WIN32_WINNT** kodunuzun desteklediği en düşük işletim sistemi sürümünü belirtir. Visual Studio ve Microsoft C++ derleyicisi, WINDOWS 7 SP1 ve üstünü hedeflemesini destekler. Daha eski araç kümeleri Windows XP SP4, Windows Server 2003 SP4, Vista ve Windows Server 2008 için destek içerir. Windows 95, Windows 98, Windows ME, Windows NT ve Windows 2000 desteklenmez.

Eski bir projeyi yükselttiğinizde, **WINVER** veya **_WIN32_WINNT** makrolarınızı güncelleştirmeniz gerekebilir. Windows 'un desteklenmeyen bir sürümü için değerler atanırsa, bu makrolarla ilgili derleme hataları görebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Makroları değiştirmek için (örneğin, Windows 'u hedefleyen bazı proje şablonlarının içerdiği *targetver. h*içinde), aşağıdaki satırları ekleyin.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

Örnekteki makrolar, Windows 10 işletim sisteminin her bir sürümünü hedeflemek üzere ayarlanır. Olası değerler, her ana Windows sürümü için makroları tanımlayan *SDKDDKVer. h*Windows üstbilgi dosyasında listelenmiştir. Uygulamanızı önceki bir Windows platformunu destekleyecek şekilde derlemek için, *WinSDKVer. h*'yi dahil edin. Ardından, **WINVER** ve **_WIN32_WINNT** makrolarını *SDKDDKVer. h*dahil etmeden önce desteklenen en eski platforma ayarlayın. Aşağıda, Windows 'un başlıca sürümlerinin değerlerini kodlayan *SDKDDKVer. h* öğesinin WINDOWS 10 SDK sürümü satırları verilmiştir:

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

Sürüm oluşturma konusunda daha ayrıntılı bir yaklaşım için, *SDKDDKVer. h*içindeki ntddı sürüm sabitlerini kullanabilirsiniz. Windows 10 SDK sürüm 10.0.18362.0 ' de *SDKDDKVer. h* tarafından tanımlanan bazı makrolar aşağıda verilmiştir:

```C
//
// NTDDI version constants
//
#define NTDDI_WIN7                          0x06010000
#define NTDDI_WIN8                          0x06020000
#define NTDDI_WINBLUE                       0x06030000
#define NTDDI_WINTHRESHOLD                  0x0A000000  /* ABRACADABRA_THRESHOLD */
#define NTDDI_WIN10                         0x0A000000  /* ABRACADABRA_THRESHOLD */
#define NTDDI_WIN10_TH2                     0x0A000001  /* ABRACADABRA_WIN10_TH2 */
#define NTDDI_WIN10_RS1                     0x0A000002  /* ABRACADABRA_WIN10_RS1 */
#define NTDDI_WIN10_RS2                     0x0A000003  /* ABRACADABRA_WIN10_RS2 */
#define NTDDI_WIN10_RS3                     0x0A000004  /* ABRACADABRA_WIN10_RS3 */
#define NTDDI_WIN10_RS4                     0x0A000005  /* ABRACADABRA_WIN10_RS4 */
#define NTDDI_WIN10_RS5                     0x0A000006  /* ABRACADABRA_WIN10_RS5 */
#define NTDDI_WIN10_19H1                    0x0A000007  /* ABRACADABRA_WIN10_19H1*/

#define WDK_NTDDI_VERSION                   NTDDI_WIN10_19H1 /* ABRACADABRA_WIN10_19H1 */

//
// masks for version macros
//
#define OSVERSION_MASK      0xFFFF0000
#define SPVERSION_MASK      0x0000FF00
#define SUBVERSION_MASK     0x000000FF

//
// macros to extract various version fields from the NTDDI version
//
#define OSVER(Version)  ((Version) & OSVERSION_MASK)
#define SPVER(Version)  (((Version) & SPVERSION_MASK) >> 8)
#define SUBVER(Version) (((Version) & SUBVERSION_MASK) )
```

**OSVer**, **Spver**ve **SUBVER** makroları, farklı API desteğinin farklı seviyelerine yönelik koşullu derlemeyi denetlemek için kodunuzda kullanılabilir.

Baktığınız *SDKDDKVer. h* dosyasında listelenen bu Windows sürümlerinin tümünü göremeyebilirsiniz. Yani, büyük olasılıkla Windows SDK eski bir sürümünü kullanıyorsunuz demektir. Varsayılan olarak, Visual Studio 'daki yeni Windows projeleri Windows 10 SDK 'sını kullanır.

> [!NOTE]
> Uygulamanıza iç MFC üstbilgileri eklerseniz, değerlerin çalışması garanti edilmez.

Ayrıca, bu makroyu `/D` derleyici seçeneğini kullanarak da tanımlayabilirsiniz. Daha fazla bilgi için bkz. [/d (Önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md).

Bu makroların anlamları hakkında daha fazla bilgi için bkz. [Windows üst bilgilerini kullanma](/windows/win32/WinProg/using-the-windows-headers).

## <a name="see-also"></a>Ayrıca bkz.

[Görsel C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)
