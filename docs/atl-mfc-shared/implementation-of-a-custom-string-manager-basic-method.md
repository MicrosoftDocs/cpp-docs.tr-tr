---
title: "Uygulama bir özel dize Yöneticisi'nin (temel yöntemi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b80af4fc8b463b6987f586c426bd465520f75ba6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Uygulama bir özel dize Yöneticisi'nin (temel yöntemi)
Dize verilerini ATL tarafından sağlanan kullanmak için bellek ayırma şeması özelleştirmek için en kolay yolu **CAtlStringMgr** sınıf ancak kendi bellek ayırma yordamlar sağlar. Oluşturucusu **CAtlStringMgr** tek bir parametre alır: gösteren bir işaretçi bir `IAtlMemMgr` nesnesi. `IAtlMemMgr`yığın için genel bir arabirim sağlayan bir Özet temel sınıftır. Kullanarak `IAtlMemMgr` arabirimi, **CAtlStringMgr** ayırır, yeniden ayırır ve dize verilerini depolamak için kullanılan belleği serbest bırakır. Her iki uygulama için `IAtlMemMgr` kendiniz arabirim veya beş sağlanan ATL bellek yöneticisi sınıflarından birini kullanın. ATL tarafından sağlanan bellek yöneticilerini yalnızca mevcut bellek ayırma tesis kaydır:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) standart CRT heap işlevleri sarmalar ([malloc](../c-runtime-library/reference/malloc.md), [ücretsiz](../c-runtime-library/reference/free.md), ve [realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) Win32 yığın işlemek, sarmalayan kullanarak [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), ve [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 API'ları sarmalar: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), ve [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 API'ları sarmalar: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), ve [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) COM görev ayırıcısı API'lerini sarmalar: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), ve [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Dize bellek yönetimi amacıyla en yararlı bir sınıftır `CWin32Heap` olduğundan, birden çok bağımsız yığınlara oluşturmanıza olanak sağlar. Örneğin, yalnızca dizeleri için ayrı bir yığın kullanmak istiyorsanız, aşağıdakileri yapabilirsiniz:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 Bu özel dize Yöneticisi için bellek yönetmek için bir `CString` değişkeni, bir parametre olarak Yöneticisi bir işaretçi geçişine `CString` değişkenin Oluşturucusu:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)

