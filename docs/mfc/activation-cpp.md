---
title: Etkinleştirme (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0f6207d91fa3816ab17462f62bd39551f7961e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383980"
---
# <a name="activation-c"></a>Etkinleştirme (C++)

Bu makalede visual OLE öğelerini düzenleme etkinleştirme rolünü açıklar. Bir kullanıcı bir OLE öğesini bir kapsayıcı belgeye gömülü sonra kullanılması gerekebilir. Bunu yapmak için bu öğeyi etkinleştiren öğesi kullanıcı çift tıkladığında. Etkinleştirme için en sık etkinlik düzenliyor. Düzenleme için etkinleştirildiğinde birçok geçerli OLE öğeleri, bu öğeyi oluşturan sunucu uygulamaya ait yansıtacak şekilde değiştirmek için geçerli çerçeve penceresindeki menüleri ve araç çubuklarını neden. Olarak yerinde etkinleştirme, bilinen bu davranış, bileşik bir belgeye ekli herhangi bir öğeye kapsayıcı belge penceresi çıkmadan düzenlemesine olanak tanır.

Katıştırılmış OLE öğeleri ayrı bir pencerede düzenlemek mümkündür. Bu, kapsayıcı veya bir sunucu uygulaması yerinde etkinleştirme desteklemiyorsa gerçekleşir. Bu durumda, kullanıcı gömülü bir öğe çift tıkladığında, sunucu uygulaması ayrı bir pencerede başlatılır ve kendi belge olarak gömülü bir öğe görünür. Kullanıcı Bu pencere öğesinde düzenler. Düzenleme tamamlandığında, kullanıcının sunucu uygulaması kapatır ve kapsayıcılı bir uygulama döndürür.

Alternatif olarak, kullanıcı "düzenleme Aç" ile seçebilir  **\<Nesne > açık** komutunu **Düzenle** menüsü. Bu nesne ayrı bir pencerede açar.

> [!NOTE]
>  Standart davranışı OLE 1 sürümünde olan ayrı bir pencerede katıştırılmış öğeleri düzenleme ve bazı OLE uygulamaları düzenleme yalnızca bu stil destekleyebilir.

Yerinde etkinleştirme belge oluşturma için belge merkezli bir yaklaşım yükseltir. Kullanıcı, tek bir varlık olarak üzerinde çalışan uygulamalar arasında geçiş olmadan bir bileşik belge davranabilirsiniz. Ancak, yalnızca bağlantılı öğeler için değil, katıştırılmış öğeler için yerinde etkinleştirme kullanılır: ayrı bir pencerede düzenlenmelidir. Bağlantılı bir öğe farklı bir yerde depolandığından budur. Düzenleme bağlantılı öğe verilerin depolandığı veri, diğer bir deyişle, gerçek bağlamında gerçekleşir. Bağlantılı bir öğe ayrı bir pencerede düzenleme, verileri başka bir belgeye ait kullanıcı anımsatır.

MFC, iç içe geçmiş yerinde etkinleştirme desteklemez. Kapsayıcı/sunucu uygulaması'oluşturma ve kapsayıcı/sunucu başka bir kapsayıcı ve yerinde etkinleştirilmiş eklenir, bunu yerinde olamaz katıştırılmış nesneleri etkinleştirin.

Kullanıcı tıkladığında gömülü bir öğe için ne öğesi için tanımlanan fiilleri bağlıdır. Bilgi için [etkinleştirme: fiiller](../mfc/activation-verbs.md).

## <a name="see-also"></a>Ayrıca Bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Sunucular](../mfc/servers.md)

