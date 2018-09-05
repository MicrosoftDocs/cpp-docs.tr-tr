---
title: Ayırma ve serbest bırakma BSTR için bellek serbest bırakma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- bstr
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bd299c228b3b388658093f6b138225c10ff38db
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751068"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
[SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)   
[SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)

