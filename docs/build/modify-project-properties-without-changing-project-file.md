---
title: 'Nasıl kullanılır: Proje dosyasını değiştirmeden C++ proje özelliklerini ve hedeflerini değiştirme'
ms.date: 11/28/2018
helpviewer_keywords:
- project properties [C++], modifying outside project file
ms.openlocfilehash: 72107b572e35f222c0b03959e0edd2d23bd0130a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328455"
---
# <a name="how-to-modify-c-project-properties-and-targets-without-changing-the-project-file"></a>Nasıl kullanılır: Proje dosyasını değiştirmeden C++ proje özelliklerini ve hedeflerini değiştirme

Proje dosyasını değiştirmeden MSBuild komut isteminden proje özelliklerini ve hedeflerini geçersiz kılabilirsiniz. Bu, bazı özellikleri geçici veya ara sıra uygulamak istediğinizde yararlıdır. Bu MSBuild bazı bilgi varsayar. Daha fazla bilgi için [MSBUild'e](https://docs.microsoft.com/visualstudio/msbuild/msbuild)bakın.

> [!IMPORTANT]
> .props veya .targets dosyasını oluşturmak için Visual Studio'daki XML Düzenleyicisini veya herhangi bir metin düzenleyicisini kullanabilirsiniz. Özellikleri proje dosyasına eklediği için bu senaryoda **Özellik Yöneticisi'ni** kullanmayın.

*Proje özelliklerini geçersiz kılmak için:*

1. Geçersiz kılmak istediğiniz özellikleri belirten bir .props dosyası oluşturun.

1. Komut isteminden: ForceImportBeforeCppTargets="C:\sources\my_props.props" kümesi

*Proje hedeflerini geçersiz kılmak için:*

1. Bir .targets dosyası nın uygulanmasıveya belirli bir hedefle birlikte oluşturulması

2. Komut istemigönderen: set ForceImportAfterCppTargets ="C:\sources\my_target.targets"

/p: seçeneğini kullanarak msbuild komut satırında her iki seçeneği de ayarlayabilirsiniz:

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props"
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets"
```

Bu şekilde özellikleri ve hedefleri geçersiz kılmak, çözümdeki tüm .vcxproj dosyalarına aşağıdaki içeri aktarımları eklemeye eşdeğerdir:

```cmd
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```
