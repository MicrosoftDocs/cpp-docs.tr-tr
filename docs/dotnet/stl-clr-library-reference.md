---
title: STL/CLR Kitaplık Başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 78dc5c57ca000dfa03dba640c46cec16aaca133f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429481"
---
# <a name="stlclr-library-reference"></a>STL/CLR Kitaplık Başvurusu

STL/CLR kitaplığı, C++ ve .NET Framework ortak dil çalışma zamanı (CLR) ile kullanmak için C++ Standart Kitaplığı'nın bir alt bir paketleme ' dir. STL/CLR ile tüm kapsayıcıları, Yineleyiciler ve algoritmalar standart kitaplığı yönetilen bir ortamda kullanabilirsiniz.

STL/CLR kullanmak için:

- Üst bilgiler dahil **cliext** yerine normal bir C++ Standart Kitaplığı eşdeğerleri alt dizini içerir.

- Kitaplık adlarıyla nitelemeniz `cliext::` yerine `std::`.

STL/CLR .NET derlemesindeki arası senaryolarda kullandığı genel türleri ve arayüzleri kullanıma sunar **Microsoft.VisualC.STLCLR.dll**. Bu DLL, .NET Framework 3.5 dahildir. STL/CLR kullanan bir uygulamayı yeniden dağıtırsanız, Kurulum projenizin bağımlılıklar bölümüne projenizin kullandığı diğer Visual C++ kitaplıklarının yanı sıra .NET Framework 3.5 gerekir.

## <a name="in-this-section"></a>Bu Bölümde

[cliext Ad Alanı](../dotnet/cliext-namespace.md)<br/>
STL/CLR kitaplığının tüm türlerini içeren ad boşluğunu anlatır.

[STL/CLR Kapsayıcıları](../dotnet/stl-clr-containers.md)<br/>
C++ Standart kapsayıcı öğeleri, eklenebilen öğe türleri ve sahiplik sorunlarını gereksinimleri dahil olmak üzere Kitaplığı ' nda bulunan kapsayıcılar genel bir bakış sağlar.

[STL/CLR Kapsayıcı Öğeleri için Gereksinimler](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
C++ Standart Kitaplığı kapsayıcılarına eklenen tüm başvuru türleri için minimum gereksinimleri açıklar.

[Nasıl yapılır: Bir .NET Koleksiyonundan STL/CLR Kapsayıcısına Dönüştürme](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
Bir .NET koleksiyonunun bir STL/CLR kapsayıcısına nasıl dönüştürüleceğini açıklar.

[Nasıl yapılır: Bir STL/CLR Kapsayıcısından .NET Koleksiyonuna Dönüştürme](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
İçin bir .NET koleksiyonunun bir STL/CLR kapsayıcısına dönüştürme işlemini açıklamaktadır.

[Nasıl yapılır: Bir Derlemeden STL/CLR Kapsayıcısı Sunma](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
C++ derlemesinde yazılmış bazı STL/CLR kapsayıcı öğeleri görüntüleme işlemini göstermektedir.

Ayrıca, bu bölümde, STL/CLR öğesinin aşağıdaki bileşenlerini de açıklanmaktadır:

|||
|-|-|
|[bağdaştırıcı (STL/CLR)](../dotnet/adapter-stl-clr.md)|[algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)|
|[deque (STL/CLR)](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|
|[functional (STL/CLR)](../dotnet/functional-stl-clr.md)|[hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)|
|[hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)|[hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)|
|[hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)|[list (STL/CLR)](../dotnet/list-stl-clr.md)|
|[map (STL/CLR)](../dotnet/map-stl-clr.md)|[multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)|
|[multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)|[numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)|
|[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)|[queue (STL/CLR)](../dotnet/queue-stl-clr.md)|
|[set (STL/CLR)](../dotnet/set-stl-clr.md)|[stack (STL/CLR)](../dotnet/stack-stl-clr.md)|
|[utility (STL/CLR)](../dotnet/utility-stl-clr.md)|[vector (STL/CLR)](../dotnet/vector-stl-clr.md)|

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)