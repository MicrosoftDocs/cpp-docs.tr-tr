---
description: 'Hakkında daha fazla bilgi edinin: STL/CLR kapsayıcı öğeleri için gereksinimler'
title: STL/CLR Kapsayıcı Öğeleri için Gereksinimler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
ms.openlocfilehash: 3696d9df40f69b1dd39205a2dc7a3b802e815841
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305513"
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR Kapsayıcı Öğeleri için Gereksinimler

STL/CLR kapsayıcılarına eklenen tüm başvuru türleri, en azından aşağıdaki öğeleri içermelidir:

- Ortak kopya Oluşturucu.

- Ortak atama işleci.

- Ortak yok edici.

Ayrıca, [set](../dotnet/set-stl-clr.md) ve [map](../dotnet/map-stl-clr.md) gibi ilişkilendirilebilir kapsayıcılar, varsayılan olarak tanımlanmış bir genel karşılaştırma operatörüne sahip olmalıdır `operator<` . Kapsayıcılardaki bazı işlemler için genel bir varsayılan Oluşturucu ve genel bir denklik işleci de gerekebilir.

Başvuru türleri gibi, ilişkilendirilebilir bir kapsayıcıya eklenecek başvuru türleri için değer türleri ve işleyiciler, tanımlı gibi bir karşılaştırma işlecine sahip olmalıdır `operator<` . Ortak kopya Oluşturucu, ortak atama operatörü ve genel yıkıcı için gereksinimler, başvuru türlerine yönelik değer türleri veya Tanıtıcılarda bulunmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
