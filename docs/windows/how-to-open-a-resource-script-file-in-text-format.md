---
title: 'Nasıl yapılır: kaynak betik dosyasını metin biçiminde açma | Microsoft Docs'
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
- resource script files, opening in text format
- .rc files, opening in text format
- rc files, opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aae516aeecd90a46544d1e9e28e1352fc73f6e2c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221466"
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>Nasıl Yapılır: Kaynak Betik Dosyasını Metin Biçiminde Açma

Belirli kaynak düzenleyicisinin içinde bir iletişim kutusu gibi bir kaynak açmaya gerek kalmadan proje kaynak betiği (.rc) dosyasının içeriğini görüntülemek istediğinizde zamanlar olabilir. Örneğin, her biri ayrı olarak açmak zorunda kalmadan kaynak dosyasındaki tüm iletişim kutuları arasında bir dize aramak isteyebilirsiniz.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

Kaynak dosyası içerdiği tüm kaynakları görüntüleme ve tarafından desteklenen genel işlemleri gerçekleştirmek için metin biçiminde kolayca açabilirsiniz [metin düzenleyici](https://msdn.microsoft.com/508e1f18-99d5-48ad-b5ad-d011b21c6ab1).

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