---
title: Web istemcisi uygulamalarını yeniden dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d036f7d46e0db84b8572b26c747947c929972517
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48889938"
---
# <a name="redistributing-web-client-applications"></a>Web İstemcisi Uygulamalarını Yeniden Dağıtma

Uygulamanız WebBrowser denetimi ekleyen MFC sınıfları kullanıyorsa (örneğin, `CHtmlView` veya `CHtmlEditView`), Microsoft Internet Explorer 4.0 veya sonraki sürümü en azından en düşük düzeyde yüklenmelidir hedef bilgisayarda.

Internet Explorer'ın en son sürümü yükleyerek de hedef bilgisayarda en son ortak denetim dosyalarına sahip olmasını sağlar. Daha fazla bilgi için [yükleme ve dağıtma, Internet Explorer 11](/internet-explorer/ie11-deploy-guide/install-and-deploy-ie11).

## <a name="see-also"></a>Ayrıca Bkz.

[Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)