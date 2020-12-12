---
description: 'Daha fazla bilgi edinin: kaynakları kopyalama proje özellikleri (Linux C++)'
title: Kaynakları kopyalama proje özellikleri (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: 9c486519e1a37a08531dae82003504838f2032a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169807"
---
# <a name="copy-sources-project-properties-linux-c"></a>Kaynakları kopyalama proje özellikleri (Linux C++)

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

Bu özellik sayfasında ayarlanan özellikler, dosya düzeyi özellikleri ayarlanmış hariç projedeki tüm dosyalar için geçerlidir.

| Özellik | Açıklama |
|--|--|
| Kopyalanacak kaynaklar | Uzak sisteme kopyalanacak kaynakları belirtir. Bu listenin değiştirilmesi, dosyaların uzak sistemde kopyalandığı dizin yapısını değişebilir veya başka bir şekilde etkileyebilir. |
| Kaynakları Kopyala | Kaynakların uzak sisteme kopyalanıp kopyalanmayacağını belirtir. |
| Kopyalanacak ek kaynaklar | Uzak sisteme kopyalanacak ek kaynakları belirtir. İsteğe bağlı olarak, yerel bir dosyanın uzak sistemdeki belirtilen uzak konuma kopyalanabilen şu şekilde bir söz dizimini kullanarak yerel-uzak eşleme çiftleri belirtebilirsiniz: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2. |

@SourcesToCopyRemotely ve @DataFilesToCopyRemotely Proje dosyasındaki öğe gruplarını inceleyin. Hangi kaynakların veya veri dosyalarının uzaktan kopyalandığını değiştirmek için *vcxproj* dosyasını aşağıdaki gibi düzenleyin:

```xml
<ItemGroup>
   <MyItems Include="foo.txt" />
   <MyItems Include="bar.txt" />
   <DataFilesToCopyRemotely Include="@(MyItems)" />
</ItemGroup>
```

::: moniker-end
