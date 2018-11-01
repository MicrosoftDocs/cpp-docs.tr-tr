---
title: Geçersiz kılma tanımlayıcıları (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: 9d839b9530cff144cda7897b0c96af48c14454a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639862"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Geçersiz kılma tanımlayıcıları (C + +/ CLI ve C + +/ CX)

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

[.NET ve UWP İçin Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)