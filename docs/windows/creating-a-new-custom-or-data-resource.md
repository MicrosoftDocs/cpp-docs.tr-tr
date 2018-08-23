---
title: Yeni özel veya veri kaynağı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- custom resources [C++]
- data resources [C++]
- resources [Visual Studio], creating
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f820991ed55efccc883fa4454a8f2ee93a82f85
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612585"
---
# <a name="creating-a-new-custom-or-data-resource"></a>Yeni Özel veya Veri Kaynağı Oluşturma

Kaynak normal kaynak betiği (.rc) dosyası sözdizimi kullanılarak ayrı bir dosyada ve bu dosyayı içeren projenize sağ tıklayarak girerek yeni bir özel veya veri kaynağı oluşturabilirsiniz **Çözüm Gezgini** tıklayıp **Kaynak içeren** kısayol menüsünde.

### <a name="to-create-a-new-custom-or-data-resource"></a>Yeni bir özel veya veri kaynağı oluşturmak için

1. [Bir .rc dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md) , özel veya veri kaynağı içeriyor.

   Null ile sonlandırılmış tırnak içine alınmış dizeler veya ondalık, onaltılık veya sekizlik biçimde tamsayılar olarak bir .rc dosyasında özel veri yazabilirsiniz.

2. İçinde **Çözüm Gezgini**, projenizin .rc dosyasını sağ tıklatın ve ardından **kaynak içerikleri** kısayol menüsünde.

3. İçinde **derleme zamanı yönergeleri** kutusuna bir `#include` özel kaynağınızı içeren dosyanın adını verir deyimi. Örneğin:

```cpp
    #include mydata.rc
 ```

   Ne tür, yazım ve söz dizimi doğru olduğundan emin olun. İçeriğini **derleme zamanı yönergeleri** kutusunu tam olarak yazdığınız şekilde kaynak betik dosyasına eklenir.

4. Tıklayın **Tamam** yaptığınız değişiklikleri kaydetmek için.

Özel bir kaynak oluşturmak için başka bir özel kaynak olarak bir dış dosya aktarmak için yoludur. Daha fazla bilgi için [alma ve verme kaynakları](../windows/how-to-import-and-export-resources.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İkili Düzenleyicisi](binary-editor.md)