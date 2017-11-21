---
title: "MFC kitaplık sürümünü otomatik bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: defaultlib
dev_langs: C++
helpviewer_keywords:
- defaultlib in MFC
- automatic links [MFC]
- MFC libraries, linking to
- linking [MFC], automatic of MFC library version
- linking [MFC]
- linking [MFC], of MFC
- MFC libraries, versions
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9c9e9967fec6d52207e87803fa2d7a2bf42ccca
ms.sourcegitcommit: 0bbc9aac12c926b2b03726ae5b4a09d916e17d6b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2017
---
# <a name="automatic-linking-of-mfc-library-version"></a>MFC Kitaplık Sürümünü Otomatik Bağlama
MFC kitaplığını doğru sürümü kitaplıkları giriş listesinde bağlayıcı için el ile belirt gerekiyordu sürümlerinde MFC (önce Visual C++ sürüm 2.0) sürüm 3.0 önce. MFC sürüm 3.0 ve üstü ile artık MFC kitaplık sürümünü el ile belirtmek gerekli değildir. Bunun yerine, MFC başlık dosyaları otomatik olarak doğru ile tanımlanmış değerlere göre MFC kitaplık sürümünü `#define`, gibi **_DEBUG** veya **_UNICODE**. MFC başlık dosyaları ekleme **/defaultlib** belirli bir MFC kitaplık sürümünü bağlamak için bağlayıcı söyleyen yönergeleri.  
  
 Örneğin, aşağıdaki kod parçası AFX gelen. H üstbilgi dosyası ya da NAFXCWD bağlamak için bağlayıcı bildirir. LIB veya NAFXCW. MFC hata ayıklama sürümü kullanmanıza bağlı olarak LIB MFC sürümü:  
  
```c++
#ifndef _UNICODE 
#ifdef _DEBUG
#pragma comment(lib, "nafxcwd.lib")
#else
#pragma comment(lib, "nafxcw.lib")
#endif
#else
#ifdef _DEBUG
#pragma comment(lib, "uafxcwd.lib")
#else
#pragma comment(lib, "uafxcw.lib")
#endif
#endif
```  
  
 MFC başlık dosyaları da MFC kitaplıkları, Win32 kitaplıkları, OLE kitaplıklarının, örneklerinden yerleşik OLE kitaplıklarının, ODBC kitaplıkları vb. dahil olmak üzere tüm gerekli kitaplıklarında bağlayın. Win32 kitaplıkları Kernel32.Lib, User32.Lib ve GDI32.Lib içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC kitaplık sürümleri](../mfc/mfc-library-versions.md)

