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
ms.openlocfilehash: cdde0f8d4edc13e8c1e1a53d8f4393dc7c2dac40
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372476"
---
# <a name="redistributing-web-client-applications"></a>Web İstemcisi Uygulamalarını Yeniden Dağıtma

Uygulamanız WebBrowser denetimi ekleyen MFC sınıfları kullanıyorsa (örneğin, `CHtmlView` veya `CHtmlEditView`), Microsoft Internet Explorer 4.0 veya sonraki sürümü en azından en düşük düzeyde yüklenmelidir hedef bilgisayarda.

Internet Explorer'ın en son sürümü yükleyerek de hedef bilgisayarda en son ortak denetim dosyalarına sahip olmasını sağlar.

En az Internet Explorer bileşenlerini yükleme hakkında bilgi, aşağıdaki Bilgi Bankası makalesi kullanılabilir:

- Q185375, nasıl yapılır: bir Internet Explorer'ın tek EXE yüklemesini oluşturma ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp))

MSDN Kitaplığı'nda veya Tabanı makalelerini bulabilirsiniz [ http://support.microsoft.com ](http://support.microsoft.com).

## <a name="see-also"></a>Ayrıca Bkz.

[Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)