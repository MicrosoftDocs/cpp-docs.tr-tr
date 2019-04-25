---
title: 'Nasıl yapılır: Proje dosyası değiştirmeden C++ proje özelliklerini ve hedefleri Değiştir'
ms.date: 11/28/2018
helpviewer_keywords:
- project properties [C++], modifying outside project file
ms.openlocfilehash: ad527d8ee69a1786be7d325571f9c9ac4f9a8574
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273345"
---
# <a name="how-to-modify-c-project-properties-and-targets-without-changing-the-project-file"></a>Nasıl yapılır: Proje dosyası değiştirmeden C++ proje özelliklerini ve hedefleri Değiştir

Proje dosyası değiştirmeden proje özellikleri ve hedefler MSBuild komut isteminden geçersiz kılabilirsiniz. Bazı özellikler geçici olarak ya da zaman zaman uygulamak istediğinizde bu kullanışlıdır. Bu, MSBuild biraz bilgi varsayar. Daha fazla bilgi için [MSBUild](https://docs.microsoft.com/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> .Props veya .targets dosyasını oluşturmak için XML Düzenleyicisi'nde Visual Studio ya da herhangi bir metin Düzenleyicisi'ni kullanabilirsiniz. Kullanmayın **özellik Yöneticisi** Bu senaryoda çünkü proje dosyasına özelliklerini ekler.

*Proje özelliklerini geçersiz kılmak için:*

1. Geçersiz kılmak istediğiniz özellikleri belirten bir .props dosyası oluşturun.

1. Komut isteminden: ForceImportBeforeCppTargets="C:\sources\my_props.props Ayarla"

*Proje hedefleri geçersiz kılmak için:*

1. Kendi uygulama veya belirli bir hedefe bir .targets dosyasında oluşturun

2. Komut isteminden: ForceImportAfterCppTargets Ayarla "C:\sources\my_target.targets" =

Ayrıca, iki seçenekten birini msbuild komut satırında/p: seçeneğini kullanarak ayarlayabilirsiniz:

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props"
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets"
```

Özellikler ve bu şekilde hedefleri geçersiz kılma, Çözümdeki tüm .vcxproj dosyaları aşağıdaki içeri aktarmaları ekleme eşdeğerdir:

```cmd
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```
