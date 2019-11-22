---
title: Kaynakları kopyalama proje özellikleri (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: bc99814e825cda091b6a0b00256ca2d8269ecdd3
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305400"
---
# <a name="copy-sources-project-properties-linux-c"></a>Kaynakları kopyalama proje özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Bu özellik sayfasında ayarlanan özellikler, dosya düzeyi özellikleri ayarlanmış hariç projedeki tüm dosyalar için geçerlidir.

Özellik | Açıklama
--- | ---
Kopyalanacak kaynaklar | Uzak sisteme kopyalanacak kaynakları belirtir. Bu listenin değiştirilmesi, dosyaların uzak sistemde kopyalandığı dizin yapısını değişebilir veya başka bir şekilde etkileyebilir.
Kaynakları Kopyala | Kaynakların uzak sisteme kopyalanıp kopyalanmayacağını belirtir.
Kopyalanacak ek kaynaklar | Uzak sisteme kopyalanacak ek kaynakları belirtir. İsteğe bağlı olarak, liste, yerel bir dosyanın uzak sistemdeki belirtilen uzak konuma kopyalanabilen şu şekilde bir sözdizimi kullanılarak uzak eşleme çiftleri olarak belirlenebilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2.

@SourcesToCopyRemotely ve @DataFilesToCopyRemotely proje dosyasındaki öğe gruplarına başvurur. Hangi kaynakların veya veri dosyalarının uzaktan kopyalandığını değiştirmek için *vcxproj* dosyasını aşağıdaki gibi düzenleyin:

```xml
<ItemGroup>
   <MyItems Include="foo.txt" />
   <MyItems Include="bar.txt" />
   <DataFilesToCopyRemotely Include="@(MyItems)" />
</ItemGroup>
```

::: moniker-end
