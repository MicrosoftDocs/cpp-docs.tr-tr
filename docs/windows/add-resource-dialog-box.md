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
ms.openlocfilehash: c420a1d72aa4ceca7d71840fcccb451b6e0aba0f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857525"
---
# <a name="add-resource-dialog-box"></a>Kaynak Ekle İletişim Kutusu
Kaynaklar için C++ Windows masaüstü uygulaması projesi eklemek için bu iletişim kutusunu kullanın.  
  
> [!NOTE]
>  Bu bilgiler, Evrensel Windows platformu uygulamaları kaynaklar için geçerli değildir. Hakkında daha fazla bilgi için bkz: [uygulama kaynakları ve kaynak yönetim sistemi](/windows/uwp/app-resources/).  
  
 **Kaynak türü**  
 Oluşturmak istediğiniz kaynak türünü belirtir.  
  
 Ek kaynaklar ortaya çıkarmak için imleci ve iletişim kutusunu kaynak kategorileri genişletebilirsiniz. Bu kaynaklar ...\Microsoft Visual Studio bulunan `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct. .Rct dosyaları eklerseniz, bu dizinde konulmalıdır veya belirtmeniz gerekir bir [yolunu](../windows/how-to-specify-include-directories-for-resources.md) bunlar için. Bu dosyaları kaynaklarında uygun kategorisi altında ikinci düzeyde sonra görünür. .Rct dosyaları ekleyebileceğiniz sayısı için önceden belirlenmiş bir sınır yoktur.  
  
 Ağaç denetimi üst düzeydeki gösterilen Visual Studio tarafından sağlanan varsayılan kaynakları kaynaklardır.  
  
 **Yeni**  
 Seçtiğiniz türüne göre bir kaynak oluşturur **kaynak türü** kutusu. Kaynak uygun Düzenleyicisi'nde açar. Bir iletişim kutusu kaynağı oluşturursanız, örneğin, açılır [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).  
  
 **İçeri Aktar**  
 Açılır **alma** içinde gezinmenizi bir kaynağa, iletişim kutusu geçerli projenize içeri aktarmak isteyeceğiniz. Bir bit eşlem, simge, imleç, HTML kaynak dosyasını, ses alabilirsiniz (. WAV) kaynak dosyası veya özel kaynak dosyası.  
  
 **Özel**  
 Açılır [yeni özel kaynak iletişim kutusu](../windows/new-custom-resource-dialog-box.md) içinde özel bir kaynak oluşturabilirsiniz. Özel kaynaklar yalnızca ikili Düzenleyicisi'nde düzenlenebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Kaynak Oluşturma](../windows/how-to-create-a-resource.md)