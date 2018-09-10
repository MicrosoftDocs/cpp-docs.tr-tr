---
title: 'Nasıl yapılır: sembolleri kaynaklarda (C++) için arama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 51b2045a1605a37fa9c0d17fdc0c9456652345bd
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314202"
---
# <a name="how-to-search-for-symbols-in-resources-c"></a>Nasıl yapılır: sembolleri kaynaklarda (C++) arama

### <a name="to-find-symbols-in-resources"></a>Semboller kaynakları bulmak için

1. Gelen **Düzenle** menüsünde seçin **sembol Bul'u**.

2. İçinde [sembol Bul iletişim kutusu](/visualstudio/ide/go-to), **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya yazın (örneğin, ID_ACCEL1) bulmak istediğiniz kısayol tuşu.

   > [!TIP]
   > Kullanılacak [normal ifadeler](/visualstudio/ide/using-regular-expressions-in-visual-studio) aramanız için kullanmalısınız [dosyalarda Bul komutu](/visualstudio/ide/reference/find-command) gelen **Düzenle** menü yerine **sembol Bul'u**komutu. Normal ifadeler etkinleştirmek için olmalıdır **kullanın: normal ifadeler** onay kutusunu seçili [Bul iletişim kutusu](/visualstudio/ide/finding-and-replacing-text). Sağındaki sağ ok düğmesine tıklayabilirsiniz **Aranan** normal arama listesini görüntülemek için kutusu. Bu listeden bir ifade seçtiğinizde, arama metni olarak geçmesidir **Aranan** kutusu.

3. Herhangi bir **Bul** seçenekleri.

4. Tıklayın **Sonrakini Bul**.

   > [!NOTE]
   > Dize, Hızlandırıcı veya ikili kaynaklar sembolleri arama yapamazsınız.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere, kaynaklara erişme, el ile ekleme hakkında bilgi için statik kaynakları görüntüleme ve kaynak atama özellikleri dizeler.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Semboller: Kaynak Tanımlayıcıları](../windows/symbols-resource-identifiers.md)  
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)