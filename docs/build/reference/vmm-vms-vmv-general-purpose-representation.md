---
description: Daha fazla bilgi edinin:/VMM,/VMs,/VMV (Genel Amaçlı temsili)
title: /VMM,-VM 'ler,-VMV (Genel Amaçlı temsili)
ms.date: 11/04/2016
f1_keywords:
- /vms
- /vmm
- /vmv
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
ms.openlocfilehash: 8c5761a2f51ec9860a4afeb7d4aacbf7f882b3f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257231"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms, /vmv (Genel Amaçlı Temsil)

[Gösterim yöntemi](vmb-vmg-representation-method.md)olarak [/VMB,/VMG (Gösterim yöntemi)](vmb-vmg-representation-method.md) seçildiğinde kullanılır. Bu seçenekler, henüz karşılaşılan olmayan sınıf tanımının devralma modelini gösterir.

## <a name="syntax"></a>Syntax

```
/vmm
/vms
/vmv
```

## <a name="remarks"></a>Açıklamalar

Seçenekler aşağıdaki tabloda açıklanmıştır.

|Seçenek|Açıklama|
|------------|-----------------|
|**/VMM**|Birden çok devralma kullanan bir sınıfın bir üyesinin bir işaretçisinin en genel gösterimini belirtir.<br /><br /> [#Pragma pointers_to_members](../../preprocessor/pointers-to-members.md) karşılık gelen [Devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişkeni **multiple_inheritance**.<br /><br /> Bu gösterim, tek devralma için gerekenden daha büyük.<br /><br /> Bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli sanal ise, derleyici bir hata oluşturur.|
|**/VMs**|Hiçbir devralma veya tek devralma kullanan bir sınıfın bir üyesinin bir işaretçisinin en genel gösterimini belirtir.<br /><br /> [#Pragma pointers_to_members](../../preprocessor/pointers-to-members.md) karşılık gelen [Devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişkeni **single_inheritance**.<br /><br /> Bu, bir sınıfın üyesine yönelik işaretçinin olası en küçük gösterimidir.<br /><br /> Bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli birden çok veya sanal ise, derleyici bir hata oluşturur.|
|**/VMV**|Sanal devralma kullanan bir sınıfın bir üyesinin bir işaretçisinin en genel gösterimini belirtir. Bir hataya neden olmaz ve varsayılan değer değildir.<br /><br /> [#Pragma pointers_to_members](../../preprocessor/pointers-to-members.md) karşılık gelen [Devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişkeni **virtual_inheritance**.<br /><br /> Bu seçenek, işaretçiyi diğer seçeneklere göre yorumlamak için daha büyük bir işaretçi ve ek kod gerektirir.|

Bu devralma modeli seçeneklerinden birini belirttiğinizde, bu model, devralma türünden bağımsız olarak ya da işaretçinin sınıftan önce veya sonra mı bildirildiği bağımsız olarak, sınıf üyelerine yönelik tüm işaretçiler için kullanılır. Bu nedenle, her zaman tek devralma sınıfları kullanıyorsanız, **/VM 'ler** ile derleme yaparak kod boyutunu azaltabilirsiniz. Bununla birlikte, en genel durumu kullanmak istiyorsanız (en büyük veri gösteriminin masrafına), **/VMV** ile derleyin.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/VMB,/VMG (temsil yöntemi)](vmb-vmg-representation-method.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
