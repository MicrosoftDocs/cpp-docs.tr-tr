---
title: STL/CLR Kapsayıcı Öğeleri için Gereksinimler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
ms.openlocfilehash: 0744d38a08dbd972b786e1cc74c112322ecf181f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428580"
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR Kapsayıcı Öğeleri için Gereksinimler

STL/CLR kapsayıcılarına eklenen tüm başvuru türleri, en azından aşağıdaki öğelere sahip olmanız gerekir:

- Genel bir kopya Oluşturucu.

- Bir ortak atama işleci.

- Genel bir yıkıcı.

Ayrıca, ilişkili kapsayıcılar gibi [ayarlamak](../dotnet/set-stl-clr.md) ve [harita](../dotnet/map-stl-clr.md) olan tanımlanan, bir genel karşılaştırma işlecine sahip olmalıdır `operator<` varsayılan olarak. Kapsayıcılarda yapılan bazı işlemler de genel bir varsayılan oluşturucu ve tanımlanması için genel bir denklik işleci gerektirebilir.

Başvuru türleri, değer türleri ve tanıtıcılar gibi başvurmak için bir karşılaştırma işleci gibi ilişkilendirilebilir bir kapsayıcı eklenecek türlere sahip olmalıdır `operator<` tanımlı. Başvuru türleri değer türleri veya tanıtıcıları için ortak bir kopya Oluşturucu, ortak bir atama işleci ve ortak yıkıcısı gereksinimlerini yok.

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)