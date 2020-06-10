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
ms.openlocfilehash: fe9ccb5b78d9a60c5b8b2a19fe0818a8e1682f00
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623118"
---
# <a name="example-of-active-document-containment-office-binder"></a>Etkin Belge Kapsama Örneği: Office Binder

Microsoft Office Bağlayıcısı etkin belge kapsayıcısına bir örnektir. Office Ciltçi, kapsayıcılar genellikle olduğu için iki birincil bölme içerir. Sol bölmede, Ciltçideki etkin belgelere karşılık gelen simgeler bulunur. Her belgeye bağlayıcı içinde *bölüm* denir. Örneğin, bir Ciltçi Word belgeleri, PowerPoint dosyaları, Excel elektronik tabloları vb. içerebilir.

Sol bölmedeki bir simgeye tıklamak ilgili etkin belgeyi etkinleştirir. Cildin sağ bölmesi daha sonra seçili etkin olan belgenin içeriğini görüntüler.

Bir ciltçide Word belgesi açar ve etkinleştirirseniz, sözcük menü çubuğu ve araç çubukları görünüm çerçevesinin üst kısmında görünür ve belgenin içeriğini herhangi bir kelime komutunu veya aracı kullanarak düzenleyebilirsiniz. Ancak, menü çubuğu, cildin ve sözcüğünün menü çubuklarının bir birleşimidir. Hem Ciltçi hem de Word **Yardım** menülerini içerdiğinden, ilgili menülerin içeriği birleştirilir. Office Ciltçi gibi etkin belge kapsayıcıları otomatik olarak **Yardım** menüsü birleştirme sağlar; daha fazla bilgi için bkz. [Yardım menüsü birleştirme](help-menu-merging.md).

Başka bir uygulama türündeki etkin bir belgeyi seçtiğinizde, cildin arabirimi etkin belgenin uygulama türüne uyacak şekilde değişir. Örneğin, bir Ciltçi Excel elektronik tablosu içeriyorsa, Excel elektronik tablosu bölümünü seçtiğinizde Ciltçideki menülerin değiştiğini gözlemleyeceksiniz.

Tabii ki, ciltler yanında diğer olası kapsayıcı türleri vardır. Dosya Gezgini, sol bölmenin bir sürücü veya ağdaki bir dizin hiyerarşik listesini göstermek için ağaç denetimi kullandığı tipik çift bölgeli arabirimi kullanır, sağ bölmede ise o anda seçili olan dizinde bulunan dosyalar görüntülenir. Çift bölenden oluşan bir Internet tarayıcısı türü (Microsoft Internet Explorer gibi), genellikle tek bir kareye sahiptir ve köprüler aracılığıyla gezinme sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin belge kapsama](active-document-containment.md)
