---
title: Standart Windows iletileri işleyicileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- afx_msg
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4ed4e022326d650b1012ad5244d8b18e9c789cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348228"
---
# <a name="handlers-for-standard-windows-messages"></a>Standart Windows İletileri İşleyicileri
Varsayılan standart Windows iletileri işleyicileri (**WM_**) sınıfında önceden `CWnd`. Sınıf kitaplığı ileti adına adları bu işleyiciler için temel alır. Örneğin, işleyici için `WM_PAINT` ileti içinde bildirilen `CWnd` olarak:  
  
 `afx_msg void OnPaint();`  
  
 **Afx_msg** anahtar sözcüğü öneren C++ etkisini **sanal** işleyicileri arasında ayrım tarafından anahtar sözcüğü `CWnd` üye işlevleri. Ancak, bu işlevler gerçekte sanal olmadığını unutmayın; Bunlar, bunun yerine ileti eşlemeleri uygulanır. İleti eşlemeleri yalnızca C++ dili için Uzantılar değil, standart Önişlemci makroları bağlıdır. **Afx_msg** anahtar sözcüğü ön işleme sonra boşluğu giderir.  
  
 Taban sınıf içinde tanımlanan bir işleyici geçersiz kılmak için yalnızca aynı prototip işleviyle, türetilmiş bir sınıf ve işleyicisi için bir ileti eşleme girdisi oluşturmak için tanımlayın. İşleyicinizi "sınıfınızın temel sınıflar hiçbirinde aynı ada sahip herhangi bir işleyicisini geçersiz kılar".  
  
 Bazı durumlarda, temel sınıfları ve Windows ileti üzerinde çalışabilir şekilde işleyicinizi geçersiz kılınan işleyici taban sınıf içinde çağırmanız gerekir. Burada temel sınıf işleyicisi geçersiz kılmada çağrıyı üzerinde koşullara bağlıdır. Bazen temel sınıf işleyicisi ilk çağırın ve bazen son. İleti kendiniz değil işlemeye seçerseniz bazen, temel sınıf işleyicisi koşullu olarak çağırın. Bazen temel sınıf işleyicisi çağrıyı sonra koşullu değeri veya temel sınıf işleyici tarafından döndürülen durum bağlı olarak, kendi işleyici kod yürütmek.  
  
> [!CAUTION]
>  Bir temel sınıf işleyicisine geçirmek istiyorsanız, bir işleyiciye geçirilen bağımsız değişkenler değiştirmek güvenli değildir. Örneğin, değişiklik isteği duyabilirsiniz `nChar` bağımsız değişkeni `OnChar` işleyicisi (büyük harfe dönüştürülecek, örneğin). Bu davranış oldukça belirsiz adıdır, ancak bu etkiyi gerçekleştirmesi gerekiyorsa da `CWnd` üye işlevi **SendMessage** yerine.  
  
 Nasıl Özellikler penceresini belirli bir ileti işleyicisi işlevi çatıyı yazdığında belirli bir ileti geçersiz kılmak için uygun şekilde belirlediğiniz — bir `OnCreate` işleyicisi `WM_CREATE`, örneğin — bu önerilen biçiminde çizimler üye işlevi geçersiz kılındı. Aşağıdaki örnek, işleyici ilk temel sınıf işleyicisi çağırın ve yalnızca -1 döndürmüyor koşuluyla devam önerir.  
  
 [!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]  
  
 Kurala göre bu işleyiciler adlarını önekiyle "." Başlangıç günü Başkalarının birkaç alırken bazı bu işleyiciler, bağımsız değişkenler almayan. Bazı dönüş türü dışında de `void`. Tüm varsayılan işleyicileri **WM_** iletileri konusunda belgelenir *MFC başvurusu* sınıfının üye işlevleri olarak `CWnd` adları başlayın "On ile." Üye işlev bildirimlerinde `CWnd` ile önek **afx_msg**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
