---
title: range_adapter (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::range_adapter
dev_langs:
- C++
helpviewer_keywords:
- range_adapter class [STL/CLR]
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a5b8a02856d7739867e3cf9f76f866a1e84efca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="rangeadapter-stlclr"></a>range_adapter (STL/CLR)
Birkaç temel sınıf kitaplığı (BCL) arabirimi uygulamak için kullanılan yineleyiciler çifti saran bir şablon sınıfı. Range_adapter BCL koleksiyonu değilmiş gibi bir STL/CLR aralığını değiştirmek için kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Iter  
 Sarmalanan yineleyiciler ile ilişkili tür.  
  
## <a name="members"></a>Üyeler  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](../dotnet/range-adapter-range-adapter-stl-clr.md)|Bir bağdaştırıcı nesnesi oluşturur.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)|Saklı yineleyici çifti yerini alır.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|Koleksiyondaki öğelerin dolaşır.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu tutar.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Koleksiyondaki yazılan öğelerin dolaşır...|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu tutar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Range_adapter sırayla bir dizi öğeleri sınırlandırmak yineleyiciler çifti depolar. Nesne sırayla öğeleri yinelemek olanak tanıyan dört BCL arabirimlerini uygular. Bu şablon sınıfı STL/CLR aralıkları BCL kapsayıcıları benzediğini yönetmek için kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/bağdaştırıcısı >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)