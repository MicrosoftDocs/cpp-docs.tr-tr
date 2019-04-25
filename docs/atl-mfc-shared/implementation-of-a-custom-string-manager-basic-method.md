---
title: Uygulama özel dize Yöneticisi (temel yöntem)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
ms.openlocfilehash: c30c08217a09f600f8801bec9f50c4341e983a6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235907"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Uygulama özel dize Yöneticisi (temel yöntem)

Dize verileri ATL tarafından sağlanan kullanmak için bellek ayırma düzeni özelleştirmek için en kolay yolu `CAtlStringMgr` sınıfı ancak kendi bellek ayırma yordamlarını sağlar. Oluşturucusu `CAtlStringMgr` tek bir parametre alır: bir işaretçi bir `IAtlMemMgr` nesne. `IAtlMemMgr` bir yığın için genel bir arabirim sunan bir soyut temel sınıftır. Kullanarak `IAtlMemMgr` arabirimi `CAtlStringMgr` ayırır, yeniden ayırır ve dize verilerini depolamak için kullanılan belleği serbest bırakır. Her iki uygulama için `IAtlMemMgr` kendiniz arabirim ya da beş ATL tarafından sağlanan bellek yöneticisi sınıflarından birini kullanın. ATL tarafından sağlanan bellek yöneticileri yalnızca mevcut bellek ayırma tesis kaydır:

- [CCRTHeap](../atl/reference/ccrtheap-class.md) standart CRT yığın işlevlerinin sarmalar ([malloc](../c-runtime-library/reference/malloc.md), [ücretsiz](../c-runtime-library/reference/free.md), ve [realloc](../c-runtime-library/reference/realloc.md))

- [CWin32Heap](../atl/reference/cwin32heap-class.md) kullanılarak bir Win32 yığınının tutamacını sarar [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc), [HeapFree](/windows/desktop/api/heapapi/nf-heapapi-heapfree), ve [HeapRealloc](/windows/desktop/api/heapapi/nf-heapapi-heaprealloc)

- [CLocalHeap](../atl/reference/clocalheap-class.md) sarmalar Win32 API'ları: [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc), [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree), ve [LocalRealloc](/windows/desktop/api/winbase/nf-winbase-localrealloc)

- [CGlobalHeap](../atl/reference/cglobalheap-class.md) sarmalar Win32 API'ları: [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc), [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree), ve [GlobalRealloc](/windows/desktop/api/winbase/nf-winbase-globalrealloc).

- [CComHeap](../atl/reference/ccomheap-class.md) COM görev ayırıcısı API'leri sarmalar: [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree), ve [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

Dize bellek yönetimi amacıyla en kullanışlı sınıftır `CWin32Heap` çünkü birden çok bağımsız yığınlar oluşturmanıza olanak sağlar. Örneğin, dizeleri için ayrı bir yığında kullanmak istiyorsanız, aşağıdakileri yapabilirsiniz:

[!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]

İçin bellek yönetmek amacıyla bu özel dize Yöneticisi'ni kullanmak için bir `CString` değişkeni, yönetici olarak bir parametre bir işaretçi geçişine `CString` değişkenin Oluşturucusu:

[!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)
