---
title: Kaynak Ekle iletişim kutusu (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.insertresource
dev_langs:
- C++
helpviewer_keywords:
- resources [C++], adding
- Add Resource dialog box [C++]
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f44a0be0fc7614ab9dd09e814e7e444ed90e8a4a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317673"
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