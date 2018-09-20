---
title: Programınızdan (C++) sürüm bilgilerine erişme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac344242a55ba9d2f3c6ec2846feb18f70bf6483
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421524"
---
# <a name="accessing-version-information-from-within-your-program-c"></a>Programınızdan (C++) sürüm bilgilerine erişme

### <a name="to-access-version-information-from-within-your-program"></a>Programınızdan sürüm bilgilerine erişmek için

1. Programınızdan sürüm bilgilerine erişmek istiyorsanız, kullanmanız [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) işlevi ve [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) işlevi.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sürüm Bilgileri Düzenleyicisi](../windows/version-information-editor.md)<br/>
[Sürüm bilgileri (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)