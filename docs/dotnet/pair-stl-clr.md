---
title: çift (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair
dev_langs:
- C++
helpviewer_keywords:
- pair class [STL/CLR]
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2d05dceaa763f8d0e33ccc86e783f66447c48b76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33160829"
---
# <a name="pair-stlclr"></a>çift (STL/CLR)
Şablon sınıfı bir değer çifti saran bir nesne tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Parametreler  
 Değer1  
 İlk sarılan değer türü.  
  
 Value2  
 İkinci sarılan değer türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)|İlk sarılan değer türü.|  
|[pair::second_type (STL/CLR)](../dotnet/pair-second-type-stl-clr.md)|İkinci sarılan değer türü.|  
  
|Üye nesnesi|Açıklama|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)|İlk depolanan değer.|  
|[pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)|İkinci depolanan değer.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](../dotnet/pair-pair-stl-clr.md)|Çifti nesnesi oluşturur.|  
|[pair::swap (STL/CLR)](../dotnet/pair-swap-stl-clr.md)|İki çift içeriğini değiştirir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](../dotnet/pair-operator-assign-stl-clr.md)|Depolanan değer çifti yerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesnesi bir değer çifti depolar. Bu şablon sınıfı iki değer tek bir nesnede birleştirmek için kullanın. Unutmayın `cliext::pair` (aşağıda açıklanmıştır) yönetilmeyen çifti depolamak için türlerini kullanın; depoları türleri yalnızca yönetilen `std::pair`bildirilen `<utility>`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/yardımcı programı >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [make_pair (STL/CLR)](../dotnet/make-pair-stl-clr.md)