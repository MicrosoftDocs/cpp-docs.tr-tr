---
title: C + +/ CLI geçiş öncüsü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++/CLI Version 2
- upgrading Visual C++ applications, Managed Extensions for C++ to Visual C++ 2005 syntax
- migration [C++], C++/CLI Version 2
- Managed Extensions for C++, upgrading syntax
- C++/CLI Version 2, managed extensions
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 88b32ea226971c0fa5b6d269a8992629c3c4de77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385437"
---
# <a name="ccli-migration-primer"></a>C++/CLI Geçiş Öncüsü

Bu, Visual C++ programınızı C++ için Yönetilen Uzantılar'dan, Visual C++'a taşıma. bir kılavuzdur.

C + +/ CLI, dinamik bileşen programlama modelini ISO-C++ Standart diline genişletir. Yeni dil yönetilen uzantılara göre önemli geliştirmeler sunar. Bu bölüm, olduğu gibi bir eşleme var olduğundan ve kendisi için hiçbir eşleme var olmayan yapıları gösterir Visual c++ için Yönetilen Uzantılar C++ dil özelliklerinin numaralandırılmış listesini ve bunların eşleme sağlar.

## <a name="in-this-section"></a>Bu Bölümde

[Değişikliklerin Anahattı (C++/CLI)](../dotnet/outline-of-changes-cpp-cli.md)<br/>
Beş genel kategori altında değişikliklerin listesini sağlayan, hızlı başvuru için İleri düzey bir özeti.

[Dil Anahtar Sözcükleri (C++/CLI)](../dotnet/language-keywords-cpp-cli.md)<br/>
Dil anahtar sözcükleri çift alt çizginin kaldırılmasını ve bağlamsal ve boşluklu anahtar sözcüklerin Tanıtımı da dahil olmak üzere, değişiklikleri anlatır.

[Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
Ortak tür sistemi (CTS) - bildirimindeki söz dizimi değişikliklerine bakar bu sınıfların, dizilerin (parametre dizisi dahil), numaralandırmalar ve benzeri bildiriminde değişiklikler içerir.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
Ölçekli özellikler, dizin özellikleri, işleçler, temsilciler ve olaylar gibi sınıf üyelerini içeren değişiklikleri gösterir.

[Değer Türleri ve Davranışları (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
Değer türleri ve yeni iç ve sabitleme işaretçileri ailesinin odaklanır. Ayrıca, birçok önemli anlamsal değişiklikleri örtük kutulama, kutulanan değer türlerinin değiştirilemezlik ve değer sınıfları dahilindeki varsayılan oluşturucu desteğinin kaldırılması gibi anlatılmaktadır.

[Genel Dil Değişiklikleri (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
Anlamsal değişiklikleri atama gösterimi desteği gibi dize değişmez değeri davranışı ve ISO-C++ ve C + arasında anlamlarında yapılan değişiklikler +/ CLI.

## <a name="see-also"></a>Ayrıca Bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)