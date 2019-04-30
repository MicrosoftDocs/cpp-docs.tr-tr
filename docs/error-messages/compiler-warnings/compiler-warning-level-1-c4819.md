---
title: Derleyici Uyarısı (düzey 1) C4819
ms.date: 04/08/2019
f1_keywords:
- C4819
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
ms.openlocfilehash: d43b49d473e7113d8cdfb89aaa6e93045e13d0f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406320"
---
# <a name="compiler-warning-level-1-c4819"></a>Derleyici Uyarısı (düzey 1) C4819

> Dosya geçerli kod sayfasında temsil edilemeyen bir karakter içeriyor (*numarası*). Dosya, veri kaybını önlemek için Unicode biçiminde kaydedin.

Dosyadaki tüm karakterleri temsil edemeyen bir kod kullanarak bir sistemde bir ANSI kaynak dosyasını derlemek C4819 gerçekleşir.

C4819 çözmek için birçok yol vardır. Basit bir yolu bir açıklamada ise, örneğin, gerekmiyorsa, soruna neden olan karakter kaldırmaktır. Kaynak kodunuz tarafından kullanılan karakter kümesini destekleyen bir Denetim Masası'ndaki sistem kod sayfası ayarlayabilirsiniz. Unicode kullanabileceğiniz [kaçış dizileri](/cpp/c-language/escape-sequences) oluşturmak için karakterler veya dizelerin yalnızca temel ANSI kullanan kaynak kodunuzdaki karakter kümesi. Son olarak, bir Unicode biçiminde bir bayt sırası işareti (BOM) olarak da bilinen bir imza ile dosyayı kaydedin.

Visual Studio için Unicode biçiminde bir dosyayı kaydetmeye seçin **dosya** > **Kaydet**. İçinde **dosyayı farklı Kaydet** iletişim kutusunda, açılır listeyi seçin **Kaydet** düğmesini tıklatın ve seçin **kodlama ile Kaydet**. Aynı dosya adına kaydederseniz, dosyayı değiştirmek istediğinizi onaylamak gerekebilir. İçinde **Gelişmiş kaydetme seçenekleri** iletişim kutusunda, dosyadaki tüm karakterleri temsil edebilen bir kodlama seçin — örneğin, **Unicode (UTF-8 imzayla) - kod sayfası 65001**— ve ardından  **Tamam**.