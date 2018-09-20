---
title: Sürüm bilgileri Düzenleyicisi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version.F1
dev_langs:
- C++
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b953343fa14d35ab387b0fd133d6e53db4551e1d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429259"
---
# <a name="version-information-editor-c"></a>Sürüm bilgileri Düzenleyicisi (C++)

Sürüm bilgileri, şirket ve ürün kimliği, bir ürün sürüm numarasını ve telif hakkı ve ticari marka bildirimini oluşur. İle **sürüm bilgisi** Düzenleyicisi, oluşturduğunuz ve sürüm bilgileri kaynağında depolanan bu verileri korumak. Sürüm bilgileri kaynağında bir uygulama tarafından gerekli değildir, ancak uygulamayı tanımlayan bilgileri toplamak için kullanışlı bir yerdir. Sürüm bilgileri de API'leri kurulum tarafından kullanılır.

Sürüm bilgileri kaynağında bir üst bloğu ve bir veya daha fazla alt blokları vardır: tek bir sabit bilgi bloğu üst ve alt (diğer diller ve/veya karakter kümesi için) bir veya daha fazla sürüm bilgi bloğu. Üst blok düzenlenebilir bir sayısal kutusu hem seçilebilir aşağı açılan listesi vardır. Alt bloklar yalnızca düzenlenebilir metin kutuları sahip.

> [!NOTE]
> Windows standart VS_VERSION_INFO adlı yalnızca bir sürümü kaynak sağlamaktır.

**Sürüm bilgisi** Düzenleyicisi olanak sağlar:

- [Sürüm bilgileri kaynağında dize düzenleme](../windows/editing-a-string-in-a-version-information-resource.md)

- [(Yeni sürüm bilgi bloğu) başka bir dil için sürüm bilgileri ekleme](../windows/adding-version-information-for-another-language.md)

- [Sürüm bilgi bloğu silinsin](../windows/deleting-a-version-information-block.md)

- [Programınızdan erişim sürüm bilgileri](../windows/accessing-version-information-from-within-your-program.md)

   > [!NOTE]
   > Kullanırken **sürüm bilgisi** düzenleyicisinde birçok örneği sağ kaynağa özgü komutların kısayol menüsünü görüntüleyin. Örneğin, bir blok üstbilgisi girişine işaret ederken tıklarsanız, kısayol menüsünü gösterir **yeni sürüm blok bilgisi** ve **sürüm blok bilgisi silme** komutları.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)