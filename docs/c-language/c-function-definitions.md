---
title: "C işlev tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c57536aed0c53e8f74ac6031632e60a403e5ce30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-function-definitions"></a>C İşlev Tanımları
Bir işlev tanımı işlevi, türü ve sayısı almak için bekliyor parametreler ve dönüş türü adını belirtir. Bir işlev tanımı ayrıca, yerel değişkenleri ve işlev yaptığı belirlemek deyimleri bildirimleri ile işlev gövdesi içerir.  
  
## <a name="syntax"></a>Sözdizimi  
 *Çeviri birim*:  
 *Dış bildirimi*  
  
 *Çeviri birim dış-bildirimi*  
  
 *Harici bildirim*: /\* yalnızca dış (dosya) kapsamında izin\*/  
 *işlev tanımı*  
  
 `declaration`  
  
 *işlev tanımı*: /\* burada Bildirimcisi olduğu işlevi bildirimcisi\*/  
 *bildirim tanımlayıcıları* kabul*özniteliği seq* kabul*bildirimcisi bildirimi listesi* kabul*bileşik deyim*  
  
 /\**özniteliği seq* Microsoft Specific * /  
  
 Prototip Parametreler şunlardır:  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları* iptal et  
  
 *tür belirteci bildirim tanımlayıcıları* iptal et  
  
 *tür niteleyicisi bildirim tanımlayıcıları* iptal et  
  
 *bildirim listesi*:  
 *bildirimi*  
  
 *bildirim listesi bildirimi*  
  
 `declarator`:  
 *İşaretçi* kabul*doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*: /\* işlevi bildirimcisi\*/  
 *doğrudan bildirimcisi***(***parametre türü listesi***)** / * yeni stil bildirimcisi      \*/  
  
 *doğrudan bildirimcisi***(***tanımlayıcı listesi* kabul**)** / * Kullanımdan kalktı stili bildirimcisi    \*/  
  
 Parametre listesi tanımında bu söz dizimini kullanır:  
  
 *parametre türü listesi*: /\* parametre listesi\*/  
 *parametre listesi*  
  
 *parametre listesi* **,...**  
  
 *parametre listesi*:  
 *parametre bildirimi*  
  
 *parametre listesi* **,***parametre bildirimi*   
  
 *parametre bildirimi*:  
 *bildirim tanımlayıcıları bildirimcisi*  
  
 *bildirim tanımlayıcıları soyut bildirimcisi* iptal et  
  
 Eski stil işlev tanımı parametre listesinde bu söz dizimini kullanır:  
  
 *tanımlayıcı listesi*: /\* kullanılan eski stil işlev tanımları ve bildirimleri\*/  
 *tanımlayıcı*  
  
 *tanımlayıcı listesi* **,***tanımlayıcısı*   
  
 İşlev gövdesi sözdizimi aşağıdaki gibidir:  
  
 *Bileşik deyim*: /\* işlev gövdesi\*/  
 **{**`declaration`-*listesi* kabul*deyimi listesi* kabul**}**   
  
 Bir işlev bildirimi değiştirebilirsiniz yalnızca depolama sınıfı tanımlayıcıları olan `extern` ve **statik**. `extern` Belirticisi güveninin işlevi diğer dosyalarından başvurulabilir; diğer bir deyişle, işlev adı için bağlayıcı dışarı aktarılır. **Statik** belirticisi güveninin işlevi diğer dosyalarından başvurulamaz; diğer bir deyişle, ad bağlayıcı tarafından verilebilir. Depolama sınıfı işlevi tanımında görünürse `extern` varsayılır. Herhangi bir durumda, işlevi her zaman tanımı noktasından dosyanın sonuna görülebilir.  
  
 İsteğe bağlı *bildirim tanımlayıcıları* ve zorunlu `declarator` birlikte işlevin dönüş türü ve adını belirtin. `declarator` Adları işlev ve işlev adı parantez tanımlayıcı birleşimidir. İsteğe bağlı *özniteliği seq* Microsoft belirli bir terminal dışı tanımlanan özelliği [işlev özniteliklerini](../c-language/function-attributes.md).  
  
 *Doğrudan bildirimcisi* (içinde `declarator` sözdizimi) tanımlanmakta işlevin adını ve parametreleri tanımlayıcısını belirtir. Varsa *doğrudan bildirimcisi* içeren bir *parametre türü listesi*, listenin tüm parametreleri türlerini belirtir. Bu tür bir bildirimcisi işlev prototipi sonraki çağrılar için işlevi de görür.  
  
 A `declaration` içinde *bildirimi listesi* işlev tanımları içeremez bir *depolama sınıfı tanımlayıcısı* dışında **kaydetmek**. *Tür belirteci* içinde *bildirim tanımlayıcıları* yalnızca sözdizimi'nin etmeyebilirsiniz **kaydetmek** depolama sınıfı değeri için belirtilen `int` türü.  
  
 *Bileşik deyim* olan yerel değişken bildirimleri, harici olarak bildirilen öğeler ve deyimleri başvuruları içeren işlev gövdesi.  
  
 Bölümler [işlev özniteliklerini](../c-language/function-attributes.md), [depolama sınıfı](../c-language/storage-class.md), [dönüş türü](../c-language/return-type.md), [parametreleri](../c-language/parameters.md), ve [işlevgövdesi](../c-language/function-body.md) işlev tanımının ayrıntılı bileşenlerini açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../c-language/functions-c.md)