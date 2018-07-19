---
title: Uygulama özel dize Yöneticisi (temel yöntem) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c393489b8b4d0353ae37a21132f66e0618b3b794
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884590"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Uygulama özel dize Yöneticisi (temel yöntem)
Dize verileri ATL tarafından sağlanan kullanmak için bellek ayırma düzeni özelleştirmek için en kolay yolu `CAtlStringMgr` sınıfı ancak kendi bellek ayırma yordamlarını sağlar. Oluşturucusu `CAtlStringMgr` tek bir parametre alır: bir işaretçi bir `IAtlMemMgr` nesne. `IAtlMemMgr` bir yığın için genel bir arabirim sunan bir soyut temel sınıftır. Kullanarak `IAtlMemMgr` arabirimi `CAtlStringMgr` ayırır, yeniden ayırır ve dize verilerini depolamak için kullanılan belleği serbest bırakır. Her iki uygulama için `IAtlMemMgr` kendiniz arabirim ya da beş ATL tarafından sağlanan bellek yöneticisi sınıflarından birini kullanın. ATL tarafından sağlanan bellek yöneticileri yalnızca mevcut bellek ayırma tesis kaydır:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) standart CRT yığın işlevlerinin sarmalar ([malloc](../c-runtime-library/reference/malloc.md), [ücretsiz](../c-runtime-library/reference/free.md), ve [realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) kullanılarak bir Win32 yığınının tutamacını sarar [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), ve [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 API'ları sarmalar: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), ve [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 API'ları sarmalar: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), ve [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) COM görev ayırıcısı API'leri sarmalar: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), ve [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Dize bellek yönetimi amacıyla en kullanışlı sınıftır `CWin32Heap` çünkü birden çok bağımsız yığınlar oluşturmanıza olanak sağlar. Örneğin, dizeleri için ayrı bir yığında kullanmak istiyorsanız, aşağıdakileri yapabilirsiniz:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 İçin bellek yönetmek amacıyla bu özel dize Yöneticisi'ni kullanmak için bir `CString` değişkeni, yönetici olarak bir parametre bir işaretçi geçişine `CString` değişkenin Oluşturucusu:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)

