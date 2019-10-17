---
title: Kaynakları kopyalama proje özellikleri (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: ceaa1240f08b83ebc83bd7fdc25a3215467eb3f1
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444949"
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
   <MyItems Include=“foo.txt” />
   <MyItems Include=“bar.txt” />
   <DataFilesToCopyRemotely Include=”@(MyItems)” />
</ItemGroup>
```

::: moniker-end
