---
title: Kaynakları (C++) Önizleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [C++], viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd5e273a07ed09f54b84d064011874533b55fb88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445834"
---
# <a name="previewing-resources"></a>Kaynakları Önizleme

Kaynaklarınızı Önizleme açmaya gerek kalmadan grafik kaynak görüntülemenize olanak sağlar. Kaynak Tanımlayıcıları sayılara değiştiğinden bunlara derlenmiş sonra Önizleme de yürütülebilir dosyalar için yararlıdır. Bu sayısal tanımlayıcıları genellikle yeterli bilgi sağlamayan olduğundan, kaynakları Önizleme hızlıca belirlemenize yardımcı olur.

Görsel düzeni aşağıdaki kaynak türlerinin önizlemesini görebilirsiniz:

- Bit eşlem

- İletişim kutusu

- Simge

- Menü

- İmleç

- Araç Çubuğu

Görsel Önizleme işlevi Hızlandırıcı, bildirimi, dize tablosu ve sürüm bilgileri kaynakları için geçerli değildir.

### <a name="to-preview-resources"></a>Kaynakları Önizleme

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) veya seçin, kaynak, örneğin, bir belge penceresi **IDD_ABOUTBOX**.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), tıklayın **özellik sayfaları** düğmesi.

   \- veya -

3. Üzerinde **görünümü** menüsünü tıklatın **özellik sayfaları**.

   **Özellik sayfası** kaynak açar, kaynak önizlemesi görüntüleniyor. Ardından **yukarı** ve **aşağı** ağaç gezinmek için ok tuşlarını denetlemek de **kaynak görünümü** ya da belge penceresini. **Özellik sayfası** açık kalır ve odaklı ve önizlemesi mümkün olan herhangi bir kaynağa göster.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Proje Dışındaki Kaynak Betik Dosyasını Açma (Tek Başına)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)