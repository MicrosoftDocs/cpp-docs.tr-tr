---
title: 'Nasıl yapılır: kaynak betik dosyasını metin biçiminde (C++) açma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2c2f73c77e86a2b23213b3b6aabdd0bc85f91586
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317075"
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>Nasıl Yapılır: Kaynak Betik Dosyasını Metin Biçiminde Açma

Belirli kaynak düzenleyicisinin içinde bir iletişim kutusu gibi bir kaynak açmaya gerek kalmadan proje kaynak betiği (.rc) dosyasının içeriğini görüntülemek istediğinizde zamanlar olabilir. Örneğin, her biri ayrı olarak açmak zorunda kalmadan kaynak dosyasındaki tüm iletişim kutuları arasında bir dize aramak isteyebilirsiniz.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

Metin biçimindeki içerir ve genel işlemleri metin düzenleyicisi tarafından desteklenen tüm kaynakları görüntülemek için kaynak dosyası kolayca açabilirsiniz.

> [!NOTE]
> Kaynak düzenleyicileri .rc doğrudan okunmaz veya `resource.h` dosyaları. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik değil bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasını ve resource.h dosyasını geçersiz kılar). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).

### <a name="to-open-a-resource-script-file-as-text"></a>Kaynak betik dosyasını metin olarak açmak için

1. Gelen **dosya** menüsünde **açık**, ardından **dosya.**

2. İçinde **açık dosya** iletişim kutusunda, metin biçiminde görüntülemek istediğiniz kaynak betik dosyasına gidin.

3. Dosyayı vurgulayın ve ardından açılan oka tıklayın **açık** düğme (düğme sağ tarafında bulunur).

4. Seçin **birlikte Aç** aşağı açılan menüden.

5. İçinde **birlikte Aç** iletişim kutusu, tıklayın **kaynak kodu (metin) Düzenleyicisi**.

6. Gelen **açık olarak** aşağı açılan listesinden **metin**.

   Kaynak açılır **kaynak kodu** Düzenleyici.

\- veya -

1. İçinde **Çözüm Gezgini**, .rc dosyasına sağ tıklayın.

2. Kısayol menüsünden **birlikte Aç...** , ardından **kaynak kodu (metin) Düzenleyicisi**.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)