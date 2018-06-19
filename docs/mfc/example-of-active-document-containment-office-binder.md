---
title: 'Etkin belge kapsama örneği: Office Binder | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7e4f82840a4c5620762ad57b5b9fa8dd7e62d0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345967"
---
# <a name="example-of-active-document-containment-office-binder"></a>Etkin Belge Kapsama Örneği: Office Binder
Microsoft Office Binder bir etkin belge kapsayıcısı örneğidir. Kapsayıcıları zamanki gibi Office Binder birincil iki bölme içerir. Sol bölmede cilt içindeki etkin belgeler karşılık simgeleri içerir. Her bir belgenin adlı bir *bölüm* bağlayıcı içinde. Örneğin, bir bağlayıcı Word belgelerini, PowerPoint dosyaları, Excel elektronik tablolar vb. içerebilir.  
  
 Sol bölmede bir simgeye tıklayarak karşılık gelen etkin belgeyi etkinleştirir. Bağlayıcı sağ bölmesinde, daha sonra şu anda seçili etkin belgesinin içeriğini görüntüler.  
  
 Açın ve bir bağlayıcı bir Word belgesinde etkinleştirmek, Word menü çubuğu ve araç çubuklarını görünüm çerçeve üstünde görünür ve belgenin içeriğini herhangi bir sözcük komut veya araç kullanarak düzenleyebilirsiniz. Ancak, menü çubuğundaki Bağlayıcısı'nın ve Word'ün menü çubukları birleşimidir. Bağlayıcı ve Word olduğundan **yardımcı** menülerden, ilgili menüleri içeriğini birleştirilir. Etkin belge kapsayıcıları Office Binder gibi otomatik olarak sağlamak **yardımcı** menü birleştirme; daha fazla bilgi için bkz: [Yardım menüsü birleştirme](../mfc/help-menu-merging.md).  
  
 Başka bir uygulama türü, bağlayıcı'nın arabirimi değişiklikleri etkin belgenin uygulama türü, uyum sağlamak için etkin bir belge seçtiğinizde. Örneğin, bir bağlayıcı Excel elektronik tablosu içeriyorsa, Excel elektronik tablo bölümü seçtiğinizde bağlayıcı menülerde değiştiğini gözlemleyin.  
  
 Elbette, bağlayıcıları yanında kapsayıcıların olası diğer tür vardır. Dosya Gezgini, sol bölmede ağaç denetimi sağ bölmede bulunan dosyalara şu anda seçili dizinde gösterirken, bir sürücü veya ağ, dizinleri hiyerarşik bir listesini görüntülemek için kullanma tipik çift bölmeli arabirimini kullanır. Bir Internet tarayıcısı türü çift bölmeli arabirimini kullanarak yerine kapsayıcı (örneğin, Microsoft Internet Explorer) genellikle tek bir çerçeveye sahiptir ve köprüleri kullanarak gezinme sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsaması](../mfc/active-document-containment.md)

