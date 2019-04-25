---
title: Ayırma ve serbest bırakma BSTR için bellek serbest bırakma
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: adc3e1efd032bb3e3e45381da24c5a5b59852375
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216975"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Ayırma ve serbest bırakma BSTR için bellek serbest bırakma

Oluştururken `BSTR`s ve bunları COM nesneleri arasında geçmek için size bellek sızıntılarını önlemek için kullandıkları bellek değerlendirmesini olarak ölçeklendirilmesini gerekir. Olduğunda bir `BSTR` arabirim içinde kalır, siz gerekir ücretsiz kendi bellek ile işiniz bittiğinde. Ancak, bir `BSTR` geçişleri dışında bir arabirim alıcı nesne kendi bellek yönetimi sorumluluğunu alır.

Genel olarak, için ayırma ve bellek serbest bırakma kurallarını ayrılan `BSTR`s aşağıdaki gibidir:

- Bekleyen bir işleve çağırdığınızda bir `BSTR` bağımsız değişkeni için bellek tahsis gerekir `BSTR` çağırmadan önce ve daha sonra serbest bırakın. Örneğin:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- Döndüren bir işlev çağırdığınızda bir `BSTR`, kendiniz dize boş olmalıdır. Örneğin:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- Döndüren bir işlev uyguladığınızda bir `BSTR`, dize tahsis ancak bunu boş değil. Alma işlevi belleği serbest bırakır. Örneğin:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)
