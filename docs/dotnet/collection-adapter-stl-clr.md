---
title: collection_adapter (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::collection_adapter
dev_langs:
- C++
helpviewer_keywords:
- collection_adapter class [STL/CLR]
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62fb5dc48175d755771960e9121c3371a0292595
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="collectionadapter-stlclr"></a>collection_adapter (STL/CLR)
STL/CLR kapsayıcı olarak kullanmak için bir .NET koleksiyonu sarmalar. A `collection_adapter` basit bir STL/CLR kapsayıcı nesne açıklayan bir şablon sınıfıdır. Bir temel sınıf kitaplığı (BCL) arabirimi sarmalar ve denetlenen dizisi yönetmek için kullandığınız bir yineleyici çifti döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 Kol  
 Sarmalanan koleksiyon türü.  
  
## <a name="specializations"></a>Uzmanlıklar  
  
|Uzmanlık|Açıklama|  
|--------------------|-----------------|  
|IEnumerable|Öğeleri arasında sıralar.|  
|ICollection|Öğeleri grubunu tutar.|  
|IList|Sıralı bir öğe grubunu tutar.|  
|IDictionary|{Anahtar, değer} kümesini bulundurmak çiftleri.|  
|IEnumerable\<değer >|Yazılı öğeleri arasında sıralar.|  
|ICollection\<değer >|Yazılı öğeleri grubunu tutar.|  
|IList\<değer >|Yazılı öğelerinin sıralı bir grup tutar.|  
|IDictionary\<değer >|Yazılı {anahtar, değer} kümesi tutar çiftleri.|  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[collection_adapter::difference_type (STL/CLR)](../dotnet/collection-adapter-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[collection_adapter::iterator (STL/CLR)](../dotnet/collection-adapter-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[collection_adapter::key_type (STL/CLR)](../dotnet/collection-adapter-key-type-stl-clr.md)|Sözlük anahtar türü.|  
|[collection_adapter::mapped_type (STL/CLR)](../dotnet/collection-adapter-mapped-type-stl-clr.md)|Sözlük değeri türü.|  
|[collection_adapter::reference (STL/CLR)](../dotnet/collection-adapter-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[collection_adapter::size_type (STL/CLR)](../dotnet/collection-adapter-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[collection_adapter::value_type (STL/CLR)](../dotnet/collection-adapter-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)|Sarmalanan BCL arabirimi belirler.|  
|[collection_adapter::begin (STL/CLR)](../dotnet/collection-adapter-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[collection_adapter::collection_adapter (STL/CLR)](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|Bir bağdaştırıcı nesnesi oluşturur.|  
|[collection_adapter::end (STL/CLR)](../dotnet/collection-adapter-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[collection_adapter::size (STL/CLR)](../dotnet/collection-adapter-size-stl-clr.md)|Öğe sayısını sayar.|  
|[collection_adapter::swap (STL/CLR)](../dotnet/collection-adapter-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[collection_adapter::operator= (STL/CLR)](../dotnet/collection-adapter-operator-assign-stl-clr.md)|Saklı BCL tanıtıcı yerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu şablon sınıfı BCL kapsayıcı bir STL/CLR kapsayıcı olarak işlemek için kullanın. `collection_adapter` Öğe dizisi sırayla denetler bir BCL arabirimi için bir tanıtıcı depolar. A `collection_adapter` nesne `X` giriş yineleyiciler çifti döndürür `X.begin()` ve `X.end()` sırada öğeleri ziyaret etmek için kullanın. Özelleştirmeleri bazıları da yazmanıza izin `X.size()` denetimli sırası uzunluğu belirlemek için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/bağdaştırıcısı >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)