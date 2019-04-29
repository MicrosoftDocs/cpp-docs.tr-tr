---
title: 'Etkin belge kapsama örneği: Office Binder'
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
ms.openlocfilehash: b06bc0f22ee71c8afbbc8feadca68895fc24a50b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358870"
---
# <a name="example-of-active-document-containment-office-binder"></a>Etkin belge kapsama örneği: Office Binder

Microsoft Office Binder etkin belge kapsayıcı örneğidir. Kapsayıcılar genellikle yaptığınız gibi bir Office Binder birincil iki bölme içerir. Sol bölmede, etkin bağlayıcı belgeleri karşılık gelen simgeler içerir. Her belge olarak adlandırılan bir *bölümü* içinde bağlayıcı. Örneğin, bir bağlayıcı Word belgeleri, PowerPoint dosyaları, Excel elektronik tabloları vb. içerebilir.

Sol bölmede bir simgeye tıklayarak karşılık gelen etkin belgeyi etkinleştirir. Bağlayıcı sağ bölmesinde, daha sonra şu anda seçili etkin belgenin içeriğini görüntüler.

Açın ve bir Word belgesinde bir bağlayıcı etkinleştirmek, Word menü çubuğu ve araç çubuklarını görünümü çerçevenin üst kısmında görünür ve belge içeriğini herhangi bir sözcük komut veya araç kullanarak düzenleyebilirsiniz. Ancak, menü çubuğunda bir menü çubukları bağlayıcı'nın ve Word'ün birleşimidir. Bağlayıcı hem sözcük olduğundan **yardımcı** menüler, ilgili menüleri içeriğini birleştirilir. Etkin belge kapsayıcıları Office Binder gibi otomatik olarak sağlamak **yardımcı** menüsü birleştirme; daha fazla bilgi için bkz. [Yardım menüsü birleştirme](../mfc/help-menu-merging.md).

Etkin belge başka bir uygulama türü, etkin belgenin uygulama türü, uyum sağlamak için bağlayıcı'nın arabirimi değişiklikleri seçtiğinizde. Örneğin, bir bağlayıcı bir Excel elektronik tablosu içeriyorsa, Excel elektronik tablosundaki bölüm seçtiğinizde bağlayıcı menülerde değiştirme gözlemleyeceksiniz.

Elbette, kapsayıcıların bağlayıcıları yanındaki diğer olası türü vardır. Dosya Gezgini'nde, sol bölmede bir ağaç denetimi sağ bölmede yer alan dosyalar şu anda seçili dizin görüntülerken bir sürücü veya ağ dizinleri hiyerarşik bir listesini görüntülemek için kullanma tipik bölmesinde çift arabirim kullanır. Bir Internet tarayıcısı türü bir çift bölmesinde arabirimi kullanarak yerine (örneğin, Microsoft Internet Explorer) kapsayıcı, genellikle tek bir çerçeveye sahiptir ve köprüler kullanarak gezinme sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin Belge Kapsaması](../mfc/active-document-containment.md)
