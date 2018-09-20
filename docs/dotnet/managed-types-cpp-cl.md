---
title: Yönetilen türler (C++-CL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 382228b9e8364d90d7929b4633744071c5eb0c77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408049"
---
# <a name="managed-types-ccl"></a>Yönetilen Türler (C++/CL)

Sözdizimi yönetilen türler ve oluşturma bildirimi ve bu tür nesneler kullanımını önemli ölçüde Yönetilen Uzantılar'dan C++ için Visual C++ için değiştirildi. Bu, ISO-C++ tür sistemi tümleştirmelerini yükseltmek yapıldı. Bu değişiklikler, aşağıdaki alt bölümlerde ayrıntılı olarak sunulur.

## <a name="in-this-section"></a>Bu Bölümde

[Yönetilen Sınıf Türü Bildirimi](../dotnet/declaration-of-a-managed-class-type.md)<br/>
Yönetilen bildirmek anlatılmaktadır `class`, `struct`, veya `interface`.

[CLR Başvuru Sınıf Nesnesi Bildirimi](../dotnet/declaration-of-a-clr-reference-class-object.md)<br/>
İzleme işleyicisi kullanarak bir başvuru sınıfı türü nesne bildirme anlatılmaktadır.

[CLR Dizisi Bildirimi](../dotnet/declaration-of-a-clr-array.md)<br/>
Bildirme ve bir diziyi başlatmaya açıklanmaktadır.

[Yapıcı Başlangıç Düzeninde Değişiklikler](../dotnet/changes-in-constructor-initialization-order.md)<br/>
Sınıf yapıcı başlangıç düzeninde önemli değişiklikler açıklanmaktadır.

[Yok Edici Anlamlarında Yapılan Değişiklikler](../dotnet/changes-in-destructor-semantics.md)<br/>
Belirleyici sonlandırma anlatılmaktadır `Finalize` karşı `Dispose`, başvuru nesneleri ve açık bir kullanım ayrımlar `Finalize`.

**Not:** temsilcileri kadar ertelenmiştir [Temsilciler ve olaylar](../dotnet/delegates-and-events.md) bunları genel konusunda bir sınıf içinde olay üyeleriyle sunmak için [sınıfta veya arabirimde üye bildirimleri (C + +/ CLI) ](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI Geçiş Öncüsü](../dotnet/cpp-cli-migration-primer.md)<br/>
[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[Diziler](../windows/arrays-cpp-component-extensions.md)