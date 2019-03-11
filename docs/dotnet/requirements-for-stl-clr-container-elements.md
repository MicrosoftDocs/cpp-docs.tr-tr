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
ms.openlocfilehash: 113624b15a0c2c6062feb7113c4771fda6d6cf39
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739397"
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR Kapsayıcı Öğeleri için Gereksinimler

STL/CLR kapsayıcılarına eklenen tüm başvuru türleri, en azından aşağıdaki öğelere sahip olmanız gerekir:

- Genel bir kopya Oluşturucu.

- Bir ortak atama işleci.

- Genel bir yıkıcı.

Ayrıca, ilişkili kapsayıcılar gibi [ayarlamak](../dotnet/set-stl-clr.md) ve [harita](../dotnet/map-stl-clr.md) olan tanımlanan, bir genel karşılaştırma işlecine sahip olmalıdır `operator<` varsayılan olarak. Kapsayıcılarda yapılan bazı işlemler de genel bir varsayılan oluşturucu ve tanımlanması için genel bir denklik işleci gerektirebilir.

Başvuru türleri, değer türleri ve tanıtıcılar gibi başvurmak için bir karşılaştırma işleci gibi ilişkilendirilebilir bir kapsayıcı eklenecek türlere sahip olmalıdır `operator<` tanımlı. Başvuru türleri değer türleri veya tanıtıcıları için ortak bir kopya Oluşturucu, ortak bir atama işleci ve ortak yıkıcısı gereksinimlerini yok.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
