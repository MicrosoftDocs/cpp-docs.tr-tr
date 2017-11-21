---
title: "STL/CLR Kitaplık Başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5906ffd662bb8b88c1c7ec42879da7f3730020f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="stlclr-library-reference"></a>STL/CLR Kitaplık Başvurusu
STL/CLR kitaplığı C++ ve .NET Framework ortak dil çalışma zamanı (CLR) ile kullanmak için C++ Standart Kitaplığı kümesini paketlenmesi ' dir. STL/CLR ile tüm kapsayıcıları, Yineleyiciler ve yönetilen bir ortamda standart kitaplığı algoritmaları kullanabilirsiniz.  
  
 STL/CLR kullanmak için:  
  
-   Üstbilgileri dahil **cliext** normal C++ Standart Kitaplığı eşdeğerleri yerine alt içerir.  
  
-   Kitaplık adları ile nitelemek `cliext::` yerine `std::`.  
  
 STL/CLR sunan .NET derlemesi içinde çapraz derleme senaryolarda kullanan genel türleri ve arabirimleri **Microsoft.VisualC.STLCLR.dll**. Bu DLL, .NET Framework 3. 5 ' dahil edilir. STL/CLR kullanan bir uygulamayı dağıtırsanız, Kurulum projenizi bağımlılıkları bölümünde projenizi kullanan herhangi bir Visual C++ kitaplıkları yanı sıra, .NET Framework 3.5 dahil etmeniz gerekir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [cliext Namespace](../dotnet/cliext-namespace.md)  
 STL/CLR kitaplığı tüm türleri içeren ad alanı açıklanır.  
  
 [STL/CLR kapsayıcıları](../dotnet/stl-clr-containers.md)  
 C++ Standart kapsayıcı öğeler, eklenebilir öğelerinin türleri ve sahipliği sorunları için gereksinimleri dahil olmak üzere Kitaplığı ' nda bulunan kapsayıcıları genel bir bakış sağlar.  
  
 [STL/CLR kapsayıcı öğeleri için gereksinimler](../dotnet/requirements-for-stl-clr-container-elements.md)  
 C++ Standart Kitaplığı kapsayıcılarına eklenen tüm başvuru türleri için en düşük gereksinimlerini açıklar.  
  
 [Nasıl yapılır: bir .NET koleksiyonundan STL/CLR kapsayıcısına dönüştürme](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 Bir .NET koleksiyon bir STL/CLR kapsayıcısına dönüştürme açıklar.  
  
 [Nasıl yapılır: bir STL/CLR kapsayıcısından .NET koleksiyonuna dönüştürme](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 STL/CLR kapsayıcı .NET koleksiyonuna dönüştürme açıklar.  
  
 [Nasıl yapılır: bir derlemeden STL/CLR kapsayıcı kullanıma sunma](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 Bir C++ derlemede yazılmış çok STL/CLR kapsayıcı öğeleri görüntülemek nasıl gösterir.  
  
 Ayrıca, bu bölümde ayrıca STL/CLR aşağıdaki bileşenlerden açıklanmaktadır:  
  
|||  
|-|-|  
|[Bağdaştırıcı (STL/CLR)](../dotnet/adapter-stl-clr.md)|[algoritma (STL/CLR)](../dotnet/algorithm-stl-clr.md)|  
|[deque (STL/CLR)](../dotnet/deque-stl-clr.md)|[her biri için](../dotnet/for-each-in.md)|  
|[işlevsel (STL/CLR)](../dotnet/functional-stl-clr.md)|[hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)|  
|[hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)|[hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)|  
|[hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)|[Liste (STL/CLR)](../dotnet/list-stl-clr.md)|  
|[eşleme (STL/CLR)](../dotnet/map-stl-clr.md)|[multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)|  
|[multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)|[sayısal (STL/CLR)](../dotnet/numeric-stl-clr.md)|  
|[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)|[sıra (STL/CLR)](../dotnet/queue-stl-clr.md)|  
|[set (STL/CLR)](../dotnet/set-stl-clr.md)|[Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)|  
|[yardımcı program (STL/CLR)](../dotnet/utility-stl-clr.md)|[vektör (STL/CLR)](../dotnet/vector-stl-clr.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)