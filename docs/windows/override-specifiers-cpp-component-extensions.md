---
title: Geçersiz kılma tanımlayıcıları (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- override specifiers, Visual C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71cafe3d73204b6a318e731d0a95f2dfcc73fa5a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600129"
---
# <a name="override-specifiers--c-component-extensions"></a>Geçersiz Kılma Tanımlayıcıları (C++ Bileşen Uzantıları)

*Geçersiz kılma tanımlayıcıları* devralınan türlerin değiştirebilir ve devralınan türlerin üyelerinin türetilmiş türlerdeki davranış.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz:

- [abstract](../windows/abstract-cpp-component-extensions.md)

- [Yeni (vtable'da yeni yuva)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](../windows/override-cpp-component-extensions.md)

- [sealed](../windows/sealed-cpp-component-extensions.md)

- [Geçersiz kılma tanımlayıcıları ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**soyut** ve **korumalı** da nerede bunlar geçersiz kılma tanımlayıcısı olarak çalışmayan tür bildirimlerinde de geçerlidir.

Taban sınıf işlevlerini açık geçersiz kılma hakkında daha fazla bilgi için bkz: [açık geçersiz kılmalar](../windows/explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliğinin yalnızca ortak dil çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

## <a name="see-also"></a>Ayrıca Bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)