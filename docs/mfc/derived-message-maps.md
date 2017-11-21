---
title: "Türetilen ileti eşlemeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e70f2298ed916db7d9c7b2d059ef7ce69b4060c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="derived-message-maps"></a>Türetilen İleti Eşlemeleri
İşleme, bir sınıfın kendi ileti denetimi iletisinde harita ileti eşleme öykü sonu değil. Ne olur sınıfı `CMyView` (türetilmiş `CView`) bir ileti için eşleşen bir giriş yok  
  
 Aklınızda `CView`, temel sınıfını `CMyView`, sırayla türetilir `CWnd`. Bu nedenle `CMyView` *olan* bir `CView` ve *olan* bir `CWnd`. Bu sınıfların her birinin kendi ileti eşlemesi vardır. "A hiyerarşisini görüntüleme" Aşağıdaki sınıfların içinde tut ancak hiyerarşik ilişkiyi gösterir şekilde aklınızda bir `CMyView` nesnesidir tüm üç sınıf özelliklere sahip tek bir nesne.  
  
 ![Bir görünüm hiyerarşisini](../mfc/media/vc38621.gif "vc38621")  
Hiyerarşisini görüntüleme  
  
 Bir ileti sınıfında eşleştirilemiyor varsa bunu `CMyView`'s ileti eşlemesi, framework hemen olduğu temel sınıfın ileti eşlemesi de arar. `BEGIN_MESSAGE_MAP` Makrosu ileti eşlemesi başlangıcında, bağımsız değişkenler olarak iki sınıf adlarını belirtir:  
  
 [!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]  
  
 İlk bağımsız değişken ileti eşlemesi ait olduğu sınıfın adı. İkinci bağımsız değişkeni hemen temel sınıfı ile bir bağlantı sunar — `CView` burada — framework kendi ileti eşlemesi çok arama yapabilmeniz için.  
  
 Taban sınıf içinde sağlanan ileti işleyicileri böylece türetilmiş sınıf tarafından devralınır. Bu tüm işleyici üye işlevleri sanal yapmaya gerek kalmadan normal sanal üye işlevleri için çok benzer.  
  
 Hiçbir işleyici temel sınıf ileti eşlemeleri hiçbirinde bulunursa, iletinin varsayılan işleme gerçekleştirilir. Bir komut iletisiyse framework sonraki komut hedefe yönlendirir. Standart bir Windows iletisiyse, ileti için uygun varsayılan pencere yordamı geçirilir.  
  
 İleti eşleme eşleşen hızlandırmak için aynı ileti yeniden alacağını olasılığı son eşleşmeleri ile framework önbelleğe alır. Bunun bir sonucu framework işlemleri iletileri oldukça verimli bir şekilde işlenmemiş ' dir. İleti eşlemeleri de daha alanı-sanal işlevleri kullanan uygulamaları daha verimlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün ileti eşlemelerini araması](../mfc/how-the-framework-searches-message-maps.md)

