---
title: Kaynak Ekle iletişim kutusu | Microsoft Docs
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
- resources [Visual Studio], adding
- Add Resource dialog box
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a48b99ad1d00fdcc184f6a3fadc772b32057f75d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601336"
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