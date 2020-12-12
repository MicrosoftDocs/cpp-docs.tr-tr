---
description: 'Daha fazla bilgi edinin: nasıl yapılır: proje dosyasını değiştirmeden C++ proje özelliklerini ve hedeflerini değiştirme'
title: 'Nasıl yapılır: proje dosyasını değiştirmeden C++ proje özelliklerini ve hedeflerini değiştirme'
ms.date: 11/28/2018
helpviewer_keywords:
- project properties [C++], modifying outside project file
ms.openlocfilehash: 91f71ccf7764307fef174d31a63583d6a3ce2aeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179869"
---
# <a name="how-to-modify-c-project-properties-and-targets-without-changing-the-project-file"></a>Nasıl yapılır: proje dosyasını değiştirmeden C++ proje özelliklerini ve hedeflerini değiştirme

Proje dosyasını değiştirmeden MSBuild komut isteminden proje özelliklerini ve hedeflerini geçersiz kılabilirsiniz. Bu, bazı özellikleri geçici olarak veya bazen uygulamak istediğinizde yararlıdır. MSBuild hakkında bazı bilgiler olduğunu varsayar. Daha fazla bilgi için bkz. [MSBuild](/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> . Props veya. targets dosyasını oluşturmak için Visual Studio 'daki XML düzenleyicisini veya herhangi bir metin düzenleyicisini kullanabilirsiniz. Bu senaryoda **Özellik Yöneticisi** kullanmayın çünkü özellikleri proje dosyasına ekler.

*Proje özelliklerini geçersiz kılmak için:*

1. Geçersiz kılmak istediğiniz özellikleri belirten bir. props dosyası oluşturun.

1. Komut isteminden: ForceImportBeforeCppTargets = "C:\sources\ my_props. props" olarak ayarlayın

*Proje hedeflerini geçersiz kılmak için:*

1. Uygulamasıyla veya belirli bir hedefle bir. targets dosyası oluşturma

2. Komut isteminden: Forceımportaftercpptargets = "C:\sources\ my_target. targets" olarak ayarlayın

Ayrıca,/p: seçeneğini kullanarak MSBuild komut satırında her iki seçeneği de ayarlayabilirsiniz:

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props"
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets"
```

Özellikleri ve hedefleri bu şekilde geçersiz kılmak, Çözümdeki tüm. vcxproj dosyalarına aşağıdaki içeri aktarmaları ekleme ile eşdeğerdir:

```cmd
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```
