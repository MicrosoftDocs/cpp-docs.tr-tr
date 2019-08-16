---
title: BSTR için bellek ayırma ve serbest bırakma
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
ms.openlocfilehash: a7a82acff959d18dcadd3a2c8516a20d60a617d3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491410"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>BSTR için bellek ayırma ve serbest bırakma

S 'yi oluşturup `BSTR`com nesneleri arasında geçirdiğinizde, bellek sızıntılarını önlemek için kullandıkları belleği düşünerek dikkatli olmanız gerekir. Bir `BSTR` arabirim içinde kaldığında, bununla işiniz bittiğinde belleğini serbest yapmanız gerekir. Ancak, bir `BSTR` arabirimden geçtiğinde, alıcı nesne bellek yönetiminin sorumluluğunu alır.

Genel olarak, için `BSTR`ayrılan belleği ayırmak ve serbest bırakmak için kurallar aşağıdaki gibidir:

- `BSTR` Bağımsız değişken bekleyen bir işleve çağırdığınızda, çağrıdan `BSTR` önce için belleği ayırmanız ve daha sonra serbest bırakmanız gerekir. Örneğin:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- Döndüren `BSTR`bir işleve çağırdığınızda dizeyi kendiniz boşaltmanız gerekir. Örneğin:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- Döndüren bir işlevi uyguladığınızda `BSTR`, dizeyi ayırın ancak serbest kullanmayın. İşlevin alınması belleği serbest bırakır. Örneğin:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT:: AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)
