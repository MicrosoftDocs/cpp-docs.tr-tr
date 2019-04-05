---
title: Geçersiz kılma tanımlayıcıları (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: c1e8e7db2879b0226eaff562f5b5b826bce14caf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029933"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Geçersiz kılma tanımlayıcıları (C + +/ CLI ve C + +/ CX)

*Geçersiz kılma tanımlayıcıları* devralınan türlerin değiştirebilir ve devralınan türlerin üyelerinin türetilmiş türlerdeki davranış.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz:

- [abstract](abstract-cpp-component-extensions.md)

- [yeni (vtable'de yeni yuva)](new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [korumalı](sealed-cpp-component-extensions.md)

- [Geçersiz kılma tanımlayıcıları ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**soyut** ve **korumalı** da nerede bunlar geçersiz kılma tanımlayıcısı olarak çalışmayan tür bildirimlerinde de geçerlidir.

Taban sınıf işlevlerini açık geçersiz kılma hakkında daha fazla bilgi için bkz: [açık geçersiz kılmalar](explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliğinin yalnızca ortak dil çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)