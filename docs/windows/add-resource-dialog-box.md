---
title: Kaynak Ekle iletişim kutusu (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.insertresource
helpviewer_keywords:
- resources [C++], adding
- Add Resource dialog box [C++]
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
ms.openlocfilehash: b20ec4a076e276c905a96c2deabd619ea10517f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503135"
---
# <a name="add-resource-dialog-box"></a>Kaynak Ekle İletişim Kutusu

Kaynakları bir C++ Windows masaüstü uygulaması projesine eklemek için bu iletişim kutusunu kullanın.

> [!NOTE]
> Bu bilgiler, Evrensel Windows platformu uygulamalarında kaynakları için geçerli değildir. Hakkında daha fazla bilgi için bkz: [uygulama kaynaklarını ve kaynak yönetim sistemi](/windows/uwp/app-resources/).

### <a name="resource-type"></a>Kaynak türü

Oluşturmak istediğiniz kaynak türünü belirtir.

Ek kaynaklar ortaya çıkarmak için imleç ve iletişim kutusunu kaynak kategorileri genişletebilirsiniz. Bu kaynaklar ...\Microsoft Visual Studio içinde bulunan `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct. .Rct dosyaları ekleme, bu dizine koymanız gerekir ya da belirtmeniz gerekir bir [yolunu](../windows/how-to-specify-include-directories-for-resources.md) bunlar için. Daha sonra bu dosyalarındaki kaynaklar ikinci düzeyde uygun kategorisi altında görünür. Ekleyebileceğiniz .rct dosyaları sayısı önceden belirlenmiş bir sınır yoktur.

Ağaç denetimi üst düzeyde gösterilen kaynağı Visual Studio tarafından sağlanan varsayılan kaynaklardır.

### <a name="new"></a>Yeni

Seçtiğiniz türüne göre bir kaynak oluşturur **kaynak türü** kutusu. Kaynak uygun Düzenleyicisi'nde açılır. Bir iletişim kutusu kaynağı oluşturursanız, örneğin, açılır [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).

### <a name="import"></a>{1&gt;İçeri Aktar&lt;1}

Açılır **alma** içinde gidebilirsiniz bir kaynağa, iletişim kutusu geçerli projenize aktarmak istediğiniz. Bir bit eşlem simgesi, imleç, HTML kaynak dosyası, ses alabilirsiniz (. WAV) kaynak dosyası veya özel kaynak dosyası.

### <a name="custom"></a>Özel

Açılır [yeni özel kaynak iletişim kutusu](../windows/new-custom-resource-dialog-box.md) içinde özel bir kaynak oluşturabilirsiniz. Özel kaynaklar yalnızca ikili düzenleyicide düzenleyebilirsiniz.

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Kaynak Oluşturma](../windows/how-to-create-a-resource.md)