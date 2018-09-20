---
title: Internet güvenliği (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f5beba4f9a33a5bd9ee93baae6176d3ea592d2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445821"
---
# <a name="internet-security-c"></a>Internet Güvenliği (C++)

Kod güvenliği geliştiriciler ve kullanıcılar Internet uygulamaları için önemli bir sorun var. Riskleri vardır: kötü amaçlı kod, üzerinde oynanmış kod ve bilinmeyen siteleri veya yazarlar koddan.

İnternet'e geliştirirken güvenlik için iki temel yaklaşım vardır. İlk "korumalı alana alma." olarak adlandırılır Bu yaklaşımda, bir uygulama belirli bir API kümesi için kısıtlı ve potansiyel olarak tehlikeli olabilecek olanlar gibi bir program, verileri bir kullanıcının bilgisayarında nereye yok edebilir ve dosya g/ç dışında tutulması. İkincisi, dijital imzalar kullanılarak uygulanır. Bu yaklaşım için "shrinkwrap" İnternet'e adlandırılır. Kod doğrulanır ve özel anahtarı/genel anahtar teknolojisi kullanılarak imzalanmış. Kod çalıştırmadan önce kodu bilinen bir kimliği doğrulanmış kaynaktan olduğunu ve imzalanmış olduğundan'ın kodunu değiştirilmediğinden emin olmak için dijital imzasını doğrulandı.

Bu durumda, uygulamanın herhangi bir zarar yapmaz ve uygulama kaynağı güven güven. İkinci, dijital imzalar, orjinalliği doğrulamak için kullanılır. Dijital imza tanımlamak ve kod yayımcısı ayrıntılarını sağlamak için kullanılan bir endüstri standardıdır. Bu teknoloji, RSA ve X.509 dahil olmak üzere standartlarını temel alır. Tarayıcılar, genellikle bunlar indirip bilinmeyen kaynaklardan gelen kodu çalıştırmak isteyip istemediklerini açmasına imkan tanıyın.


## <a name="see-also"></a>Ayrıca Bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

