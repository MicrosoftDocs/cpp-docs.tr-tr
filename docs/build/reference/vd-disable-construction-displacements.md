---
title: -vd (oluşturma yer değiştirmelerini devre dışı bırak) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vd
dev_langs:
- C++
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e36607d362ded227199d0e12770715c52384a26
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700888"
---
# <a name="vd-disable-construction-displacements"></a>/vd (Yapı Yer Değiştirmelerini Devre Dışı Bırak)

## <a name="syntax"></a>Sözdizimi

```
/vdn
```

## <a name="arguments"></a>Arguments

**0**<br/>
Vtordisp Oluşturucu/yıkıcı yer değiştirme üyesinin eklenmesini engeller. Bu seçenek yalnızca tüm sınıf oluşturucularının ve yıkıcılarının sanal çağrı eminseniz neredeyse İşlevler'i seçin.

**1**<br/>
Gizli vtordisp Oluşturucu/yıkıcı yer değiştirme üyeleri oluşturulmasını sağlar. Bu seçim varsayılandır.

**2**<br/>
Kullanmanıza olanak tanır [dynamic_cast işleci](../../cpp/dynamic-cast-operator.md) yapılandırılmakta olan bir nesne üzerinde. Örneğin, sanal bir temel sınıftan türetilmiş bir sınıf dynamic_cast.

**/ vd2** sanal işlevler içeren sanal bir temel olduğunda vtordisp alan ekler. **/ vd1** yeterli olur. En sık karşılaşılan durum nerede **/vd2** gereklidir, sanal temel yalnızca sanal işlev bir yok edici olduğunda.

## <a name="remarks"></a>Açıklamalar

Bu seçenekler, yalnızca sanal temeller kullanan C++ kodu için geçerlidir.

Visual C++, C++ yapı öteleme desteği sanal devralma kullanıldığı durumlarda uygular. Oluşturma yer değiştirmelerini oluşturulan bir sanal temel bildirildi ve türetilen bir sınıfta geçersiz kılınmış sanal bir işlev, sorunu çözmek için oluşturucudan daha fazla türetilmiş bir sınıf bir oluşumu sırasında çağrılır.

Sanal işlev yanlış bir geçirilebilir olduğunu sorun `this` işaretçi sonuç olarak, yapı yer değiştirmelerini bırak sanal arasında tutarsızlık tabanları bir sınıf ve türetilmiş sınıflarının için yapı yer değiştirmelerini bırak. Vtordisp alana bir sınıf için her sanal temel olarak adlandırılan tek bir yapı öteleme ayarlama, çözümü sağlar.

Kod, kullanıcı tanımlı oluşturucular ve Yıkıcılar tanımlar ve ayrıca sanal temellere sanal işlevleri geçersiz kılar, varsayılan olarak, vtordisp alanları sunulmuştur.

Bu seçenekler, tüm kaynak dosyalarını etkiler. Kullanım [vtordisp](../../preprocessor/vtordisp.md) gösterme ve ardından vtordisp alanlarını sınıf sınıf olarak yeniden etkinleştirin.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)