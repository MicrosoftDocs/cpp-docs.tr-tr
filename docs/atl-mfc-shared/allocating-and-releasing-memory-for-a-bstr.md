---
title: Ayırma ve belleğin için BSTR bırakılması | Microsoft Docs
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
ms.openlocfilehash: 46ab5ae9d6f0bfa98231cbc41aa4ae0d10b89537
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Ayırma ve için BSTR belleği serbest bırakma
Oluşturduğunuzda `BSTR`s ve bunları COM nesneleri arasında geçişi, kullandıkları bellek sızıntıları önlemek için bellek değerlendirmesini ilgilenebilmek gerekir. Zaman bir `BSTR` bir arabirim içinde kalır, siz gerekir serbest kendi bellek ile bittiğinde. Ancak, bir `BSTR` geçişleri arabirim dışında alıcı nesnesini alır kendi bellek yönetimi sorumluluğunu.  
  
 Genel olarak, ayırma ve belleği serbest bırakma kuralları için ayrılan `BSTR`s aşağıdaki gibidir:  
  
-   Bekleyen bir işlevdeki çağırdığınızda bir `BSTR` bağımsız değişkeni için bellek tahsis gerekir `BSTR` çağırmadan önce ve daha sonra bırakın. Örneğin:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   Döndüren bir işlev çağırdığınızda bir `BSTR`, kendiniz dize boş olmalıdır. Örneğin:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   Uygulama zaman döndüren bir işlev bir `BSTR`, dize tahsis ancak bunu boş değil. Alma işlevinin belleği serbest bırakır. Örneğin:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
 [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx)   
 [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx)

