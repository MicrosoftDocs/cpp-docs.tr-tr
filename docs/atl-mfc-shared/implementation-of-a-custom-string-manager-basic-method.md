---
description: 'Daha fazla bilgi edinin: özel bir dize yöneticisinin uygulanması (temel yöntem)'
title: Özel bir dize Yöneticisi (temel yöntem) uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
ms.openlocfilehash: e532312edff16229b6b91eef1d95ae764b70eb5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166960"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Özel bir dize Yöneticisi (temel yöntem) uygulama

Dize verileri için bellek ayırma şemasını özelleştirmenin en kolay yolu, ATL tarafından sağlanmış sınıfı kullanmaktır, `CAtlStringMgr` ancak kendi bellek ayırma yordamlarını sağlar. İçin Oluşturucu `CAtlStringMgr` tek bir parametre alır: bir `IAtlMemMgr` nesnenin işaretçisi. `IAtlMemMgr` , bir yığına genel arabirim sağlayan soyut bir temel sınıftır. Arabirimini kullanarak, `IAtlMemMgr` `CAtlStringMgr` dize verilerini depolamak için kullanılan belleği ayırır, yeniden konumlandırır ve serbest bırakır. `IAtlMemMgr`Arabirimi kendiniz uygulayabilir ya da ATL tarafından belirtilen beş bellek Yöneticisi sınıfından birini kullanabilirsiniz. ATL tarafından sağlanmış bellek yöneticileri yalnızca var olan bellek ayırma olanaklarını sarmalıdır:

- [CCRTHeap](../atl/reference/ccrtheap-class.md) Standart CRT yığın işlevlerini ([malloc](../c-runtime-library/reference/malloc.md), [ücretsiz](../c-runtime-library/reference/free.md)ve [realloc](../c-runtime-library/reference/realloc.md)) kaydırır

- [CWin32Heap](../atl/reference/cwin32heap-class.md) [Heapayırma](/windows/win32/api/heapapi/nf-heapapi-heapalloc), [HeapFree](/windows/win32/api/heapapi/nf-heapapi-heapfree)ve [HeapReAlloc](/windows/win32/api/heapapi/nf-heapapi-heaprealloc) kullanarak bir Win32 yığın tanıtıcısını sarar

- [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 API 'Lerini sarmalanmış: [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc), [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree)ve [LocalReAlloc](/windows/win32/api/winbase/nf-winbase-localrealloc)

- [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 API 'Lerini sarmalanmış: [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc), [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)ve [GlobalReAlloc](/windows/win32/api/winbase/nf-winbase-globalrealloc).

- [CComHeap](../atl/reference/ccomheap-class.md) COM görev ayırıcısı API 'Lerini sarmalanmış: [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)ve [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

Dize bellek yönetiminin amacı için en yararlı sınıf, `CWin32Heap` birden çok bağımsız Heap oluşturmanıza olanak sağlamaktır. Örneğin, yalnızca dizeler için ayrı bir yığın kullanmak isterseniz, aşağıdakileri yapabilirsiniz:

[!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]

Bu özel dize Yöneticisi 'ni bir değişken için belleği yönetmek üzere kullanmak için `CString` , bir işaretçiyi değişkenin oluşturucusuna parametre olarak geçirin `CString` :

[!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CStringT ile bellek yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)
