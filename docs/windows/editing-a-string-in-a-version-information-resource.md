---
title: (C++) sürüm bilgileri kaynağında dize düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- version information resources [C++]
- resources [C++], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c5cc7da4629ba00bbb1c48d764b836897c0b3748
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316984"
---
# <a name="editing-a-string-in-a-version-information-resource-c"></a>(C++) sürüm bilgileri kaynağında dize düzenleme

### <a name="to-edit-a-string-in-a-version-information-resource"></a>Sürüm bilgileri kaynağında dize düzenleme

1. Öğe bir kez düzenlemeye başlamak için daha sonra tekrar seçmek için tıklayın. Doğrudan bir değişiklik **sürüm bilgisi** tablo veya [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Her iki yerde de yaptığınız değişiklikler yansıtılır.

   > [!NOTE] 
   > Düzenleme yaparken `FILEFLAGS` anahtarını **sürüm bilgisi** Düzenleyicisi seçeneğinde, ayarlayamıyor **hata ayıklama**, **özel derleme**, veya **özel Derleme** özellikleri (içinde **özellikleri** pencere) .rc dosyası için:

   - **Sürüm bilgisi** Düzenleyicisi kümeleri **hata ayıklama** özelliğiyle bir `#ifdef` kaynak kodda temel alarak `_DEBUG` bayrağı oluşturun.

   - Varsa `Private Build` anahtara sahip bir **değer** kümesinde **sürüm bilgisi** tablosundaki karşılık gelen **özel derleme** özelliği (içinde **özellikleri**  pencere) için `FILEFLAGS` anahtar olacaktır **True**. Varsa **değer** olan özelliği boş olacaktır **False**. Benzer şekilde, **özel yapı** anahtarı (içinde **sürüm bilgisi** tablo) bağlıdır **özel yapı** özelliği `FILEFLAGS` anahtarı.

Bir anahtar veya değer sütun başlıklarını tıklayarak dize blok bilgi dizisini sıralayabilirsiniz. Bu başlıkları seçili sıra bilgilerini otomatik olarak yeniden düzenleyin.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sürüm Bilgileri Düzenleyicisi](../windows/version-information-editor.md)  
[Sürüm bilgileri (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)