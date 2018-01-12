---
title: "WINVER ve _WIN32_WINNT değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 09/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- WINVER in an upgraded Visual C++ project
- _WIN32_WINNT in an upgraded Visual C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 298fc14c57ad006228da39d1eb7d664debebd904
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modifying-winver-and-win32winnt"></a>WINVER ve _WIN32_WINNT'de Değişiklik Yapma

Visual C++ artık hedefleme Windows 95, Windows 98, Windows ME, Windows NT veya Windows 2000 destekler. Varsa, **WINVER** veya **_WIN32_WINNT** makroları Windows'un bu sürümlerinde birine atanır, makroları değiştirmeniz gerekir. Visual C++ önceki bir sürümü kullanılarak oluşturulmuş bir proje yükselttiğinizde, ilgili derleme hataları görebilirsiniz **WINVER** veya **_WIN32_WINNT** bir sürümüne atanmışsa makroları Artık desteklenmeyen Windows.  
  
## <a name="remarks"></a>Açıklamalar  

Makroları değiştirmek için bir üstbilgi dosyası (Windows hedefleyen bir proje oluşturduğunuzda, bulunan Örneğin, targetver.h), aşağıdaki satırları ekleyin.  
  
```C  
#define WINVER 0x0A00  
#define _WIN32_WINNT 0x0A00  
```  
  
Bu, Windows 10 işletim sistemini hedefler. Bu değerler, ayrıca her Windows sürümü için makrolar tanımlar SDKDDKVer.h Windows üstbilgi dosyasında listelenir. Eklemeniz gereken # SDKDDKVer.h eklemeden önce define. Her Windows sürümü için değerleri kodlamak SDKDDKVer.h Windows 10 sürümü satırlarından şunlardır:  
  
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
  
Windows'un bu sürümlerinde tümünün görüntülemekte olduğunuz SDKDDKVer.h kopyasını listelenen görmüyorsanız, büyük olasılıkla Windows SDK'sı daha eski bir sürümü kullanıyor. Varsayılan olarak, Visual Studio 2017 Win32 projelerde Windows 10 SDK'yı kullanın.   
  
> [!NOTE]
>  Değerleri, uygulamanızda iç MFC başlıkları dahil ederseniz çalışmaya garanti edilmez.  
  
Kullanarak bu makrosu tanımlayabilirsiniz **/D** derleyici seçeneği. Daha fazla bilgi için bkz: [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md).  
  
Bu makroları anlamları hakkında daha fazla bilgi için bkz [anlamıyla](https://msdn.microsoft.com/library/windows/desktop/aa383745).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ değişiklik geçmişi](..\porting\visual-cpp-change-history-2003-2015.md)
