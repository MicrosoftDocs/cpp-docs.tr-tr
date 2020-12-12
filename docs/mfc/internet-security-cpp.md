---
description: 'Daha fazla bilgi edinin: Internet güvenliği (C++)'
title: Internet Güvenliği (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 870695abc89ba022a333829ec974d2f1e9147a53
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335854"
---
# <a name="internet-security-c"></a>Internet Güvenliği (C++)

Kod güvenliği, geliştiriciler ve Internet uygulamaları kullanıcılarına yönelik önemli bir sorundur. Riskler vardır: kötü amaçlı kod, üzerinde oynanmış kod ve bilinmeyen sitelerden veya yazarların kodu.

Internet için geliştirme sırasında güvenliğe yönelik iki temel yaklaşım vardır. Birincisi "korumalı alana alma" olarak adlandırılır. Bu yaklaşımda, bir uygulama belirli bir API kümesiyle kısıtlıdır ve bir programın bir kullanıcının bilgisayarında verileri bozmasına neden olabilecek dosya g/ç gibi tehlikeli olabilir. İkincisi, dijital imzalar kullanılarak uygulanır. Bu yaklaşım, Internet için "shrınkwrap" olarak adlandırılır. Kod doğrulanır ve özel anahtar/ortak anahtar teknolojisi kullanılarak imzalandı. Kod çalıştırılmadan önce, kodun bilinen kimliği doğrulanmış bir kaynaktan olduğundan ve kodun imzalandıktan sonra değiştirilmediğinden emin olmak için dijital imzası doğrulanır.

İlk durumda, uygulamanın herhangi bir zarar yapamayacak ve uygulamanın kaynağına güveneceğinizdeki güvenirsiniz. İkinci olarak, dijital imzalar özgünlük doğrulaması için kullanılır. Dijital imzalama, kodun yayıncısı hakkındaki ayrıntıları belirlemek ve sağlamak için kullanılan bir sektör standardıdır. Teknolojisi, RSA ve X. 509.440 dahil standartlara dayanır. Tarayıcılar genellikle kullanıcıların bilinmeyen kaynak kodunu indirmek ve çalıştırmak istediklerinde seçmesine izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet programlama görevleri](mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](mfc-internet-programming-basics.md)
