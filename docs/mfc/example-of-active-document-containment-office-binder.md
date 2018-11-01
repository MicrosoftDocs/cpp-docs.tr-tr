---
title: 'Etkin Belge Kapsama Örneği: Office Binder'
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
ms.openlocfilehash: 032b2cb39d75c108239d882039f7c797a357a6bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616656"
---
# <a name="example-of-active-document-containment-office-binder"></a>Etkin Belge Kapsama Örneği: Office Binder

Microsoft Office Binder etkin belge kapsayıcı örneğidir. Kapsayıcılar genellikle yaptığınız gibi bir Office Binder birincil iki bölme içerir. Sol bölmede, etkin bağlayıcı belgeleri karşılık gelen simgeler içerir. Her belge olarak adlandırılan bir *bölümü* içinde bağlayıcı. Örneğin, bir bağlayıcı Word belgeleri, PowerPoint dosyaları, Excel elektronik tabloları vb. içerebilir.

Sol bölmede bir simgeye tıklayarak karşılık gelen etkin belgeyi etkinleştirir. Bağlayıcı sağ bölmesinde, daha sonra şu anda seçili etkin belgenin içeriğini görüntüler.

Açın ve bir Word belgesinde bir bağlayıcı etkinleştirmek, Word menü çubuğu ve araç çubuklarını görünümü çerçevenin üst kısmında görünür ve belge içeriğini herhangi bir sözcük komut veya araç kullanarak düzenleyebilirsiniz. Ancak, menü çubuğunda bir menü çubukları bağlayıcı'nın ve Word'ün birleşimidir. Bağlayıcı hem sözcük olduğundan **yardımcı** menüler, ilgili menüleri içeriğini birleştirilir. Etkin belge kapsayıcıları Office Binder gibi otomatik olarak sağlamak **yardımcı** menüsü birleştirme; daha fazla bilgi için bkz. [Yardım menüsü birleştirme](../mfc/help-menu-merging.md).

Etkin belge başka bir uygulama türü, etkin belgenin uygulama türü, uyum sağlamak için bağlayıcı'nın arabirimi değişiklikleri seçtiğinizde. Örneğin, bir bağlayıcı bir Excel elektronik tablosu içeriyorsa, Excel elektronik tablosundaki bölüm seçtiğinizde bağlayıcı menülerde değiştirme gözlemleyeceksiniz.

Elbette, kapsayıcıların bağlayıcıları yanındaki diğer olası türü vardır. Dosya Gezgini'nde, sol bölmede bir ağaç denetimi sağ bölmede yer alan dosyalar şu anda seçili dizin görüntülerken bir sürücü veya ağ dizinleri hiyerarşik bir listesini görüntülemek için kullanma tipik bölmesinde çift arabirim kullanır. Bir Internet tarayıcısı türü bir çift bölmesinde arabirimi kullanarak yerine (örneğin, Microsoft Internet Explorer) kapsayıcı, genellikle tek bir çerçeveye sahiptir ve köprüler kullanarak gezinme sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Etkin Belge Kapsaması](../mfc/active-document-containment.md)

