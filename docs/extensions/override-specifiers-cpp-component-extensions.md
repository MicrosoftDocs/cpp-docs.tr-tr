---
description: 'Daha fazla bilgi edinin: geçersiz kılma tanımlayıcıları (C++/CLı ve C++/CX)'
title: Geçersiz Kılma Tanımlayıcıları (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: ce0b9ad4464eef66bc71826825e8129ef0a24cab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257595"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Geçersiz Kılma Tanımlayıcıları (C++/CLI ve C++/CX)

*Geçersiz kılma belirticileri* devralınan türlerin ve devralınan türlerin üyelerinin türetilmiş türlerde nasıl davranacağını değiştirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Geçersiz kılma belirticileri hakkında daha fazla bilgi için bkz.

- [Soyut](abstract-cpp-component-extensions.md)

- [yeni (vtable'de yeni yuva)](new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- [Geçersiz kılma belirticileri ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**abstract** ve **Sealed** , geçersiz kılma belirticileri olarak davranmayan tür bildirimlerinde de geçerlidir.

Temel sınıf işlevlerini açıkça geçersiz kılma hakkında daha fazla bilgi için bkz. [Açık geçersiz kılmalar](explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliği için yalnızca Windows Çalışma Zamanı uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliği için yalnızca ortak dil çalışma zamanına uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
