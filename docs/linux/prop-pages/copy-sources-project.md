---
title: Copy Sources Proje Özellikleri (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: 732a13520a223f1aa73733cd4098c247052f8d3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79441379"
---
# <a name="copy-sources-project-properties-linux-c"></a>Copy Sources Proje Özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Bu özellik sayfasında ayarlanan özellikler, dosya düzeyi özellikleri ayarlananlar dışında projedeki tüm dosyalar için geçerlidir.

| Özellik | Açıklama |
|--|--|
| Kopyalanması Gereken Kaynaklar | Uzak sisteme kopyalamak için kaynakları belirtir. Bu listeyi değiştirmek, dosyaların uzak sistemde kopyalandığı dizin yapısını değiştirebilir veya başka şekilde etkileyebilir. |
| Kaynakları Kopyala | Kaynakları uzak sisteme kopyalayıp kopyalamayacağını belirtir. |
| Kopyalanması gereken ek kaynaklar | Uzak sisteme kopyalamak için ek kaynaklar belirtir. İsteğe bağlı olarak, bunun gibi bir sözdizimini kullanarak yerel den uzak eşleme çiftleri belirtin: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, yerel bir dosyanın uzak sistemde belirtilen uzak konuma kopyalanabileceği. |

@SourcesToCopyRemotelyve @DataFilesToCopyRemotely proje dosyasındaki madde gruplarına bakın. Hangi kaynakların veya veri dosyalarının uzaktan kopyalanabilen bir değişiklik yapmak *için, vcxproj* dosyasını şu şekilde edin:

```xml
<ItemGroup>
   <MyItems Include="foo.txt" />
   <MyItems Include="bar.txt" />
   <DataFilesToCopyRemotely Include="@(MyItems)" />
</ItemGroup>
```

::: moniker-end
