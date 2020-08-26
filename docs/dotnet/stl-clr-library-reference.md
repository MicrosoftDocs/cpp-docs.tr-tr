---
title: STL/CLR Kitaplık Başvurusu
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
ms.openlocfilehash: e6804dab814eca4ecc5fd23c74cbbb21eac3be77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839705"
---
# <a name="stlclr-library-reference"></a>STL/CLR Kitaplık Başvurusu

STL/CLR kitaplığı, c++ ve .NET Framework ortak dil çalışma zamanı (CLR) ile kullanılmak üzere C++ standart kitaplık kapsayıcılarına benzer bir arabirim sağlar. STL/CLR, C++ standart kitaplığının Microsoft uygulamasından tamamen ayrıdır. STL/CLR eski destek için korunur, ancak C++ standardına göre güncel tutulmamaktadır. Mümkün olduğunda STL/CLR yerine yerel [C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md) kapsayıcıları kullanmanızı kesinlikle öneririz.

STL/CLR kullanmak için:

- Her zamanki C++ standart kitaplık eşdeğerleri yerine **cliext** içerme alt dizininden üstbilgileri ekleyin.

- Kitaplık adlarını `cliext::` yerine kullanın `std::` .

STL/CLR kitaplığı, C++ ve .NET Framework ortak dil çalışma zamanı (CLR) ile kullanılmak üzere STL benzeri bir arabirim sağlar. Bu kitaplık eski destek için korunur, ancak C++ standardına göre güncel tutulmamaktadır. STL/CLR yerine yerel [C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md) kapsayıcıları kullanmanızı kesinlikle öneririz.

## <a name="in-this-section"></a>Bu Bölümde

[clienext ad alanı](../dotnet/cliext-namespace.md)<br/>
STL/CLR kitaplığının tüm türlerini içeren ad alanını açıklar.

[STL/CLR kapsayıcıları](../dotnet/stl-clr-containers.md)<br/>
C++ standart kitaplığı 'nda bulunan kapsayıcılar, kapsayıcı öğelerine yönelik gereksinimler, eklenebilecek öğe türleri ve sahiplik sorunları dahil olmak üzere bir genel bakış sağlar.

[STL/CLR kapsayıcı öğeleri için gereksinimler](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
C++ standart kitaplık kapsayıcılarına eklenen tüm başvuru türleri için minimum gereksinimleri açıklar.

[Nasıl yapılır: bir .NET koleksiyonundan STL/CLR kapsayıcısına dönüştürme](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
Bir .NET koleksiyonunun bir STL/CLR kapsayıcısına nasıl dönüştürüleceğini açıklar.

[Nasıl yapılır: STL/CLR Kapsayıcısından .NET koleksiyonuna dönüştürme](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
Bir STL/CLR kapsayıcısının bir .NET koleksiyonuna nasıl dönüştürüleceğini açıklar.

[Nasıl yapılır: bir derlemeden STL/CLR kapsayıcısını kullanıma sunma](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
Bir C++ derlemesinde yazılmış çeşitli STL/CLR kapsayıcılarının öğelerinin nasıl görüntüleneceğini gösterir.

Ayrıca, bu bölümde STL/CLR 'nin aşağıdaki bileşenleri de açıklanmaktadır:

:::row:::
   :::column span="":::
      [`adapter` (STL/CLR)](../dotnet/adapter-stl-clr.md)\
      [`algorithm` (STL/CLR)](../dotnet/algorithm-stl-clr.md)\
      [`deque` (STL/CLR)](../dotnet/deque-stl-clr.md)\
      [`for each`, `in`](../dotnet/for-each-in.md)\
      [`functional` (STL/CLR)](../dotnet/functional-stl-clr.md)\
      [`hash_map` (STL/CLR)](../dotnet/hash-map-stl-clr.md)\
      [`hash_multimap` (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)\
      [`hash_multiset` (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)\
      [`hash_set` (STL/CLR)](../dotnet/hash-set-stl-clr.md)\
      [`list` (STL/CLR)](../dotnet/list-stl-clr.md)\
   :::column-end:::
   :::column span="":::
      [`map` (STL/CLR)](../dotnet/map-stl-clr.md)\
      [`multimap` (STL/CLR)](../dotnet/multimap-stl-clr.md)\
      [`multiset` (STL/CLR)](../dotnet/multiset-stl-clr.md)\
      [`numeric` (STL/CLR)](../dotnet/numeric-stl-clr.md)\
      [`priority_queue` (STL/CLR)](../dotnet/priority-queue-stl-clr.md)\
      [`queue` (STL/CLR)](../dotnet/queue-stl-clr.md)\
      [`set` (STL/CLR)](../dotnet/set-stl-clr.md)\
      [`stack` (STL/CLR)](../dotnet/stack-stl-clr.md)\
      [`utility` (STL/CLR)](../dotnet/utility-stl-clr.md)\
      [`vector` (STL/CLR)](../dotnet/vector-stl-clr.md)\
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)
