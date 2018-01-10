---
title: "Kaynak Ekle iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.insertresource
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio], adding
- Add Resource dialog box
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fde90f5d7c7822155e36b77c74cd80cdf56b10d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="add-resource-dialog-box"></a>Kaynak Ekle İletişim Kutusu
Kaynaklar için C++ Windows masaüstü uygulaması projesi eklemek için bu iletişim kutusunu kullanın.  
  
> [!NOTE]
>  Bu bilgiler, Windows mağazası uygulamalarında kaynakları için geçerli değildir. Hakkında daha fazla bilgi için bkz: [tanımlama uygulama kaynakları](http://msdn.microsoft.com/en-us/476ea844-632c-4467-9ce3-966be1350dd4).  
  
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