---
title: "Proje dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .vcproj files
- Visual C++ projects, project file format
- VCPROJ (Visual C++ project file) format
- project files [C++], .vcproj file format
ms.assetid: 5261cf45-3136-40a6-899e-dc1339551401
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac1b6d01bc454e2bcc7f1c8fd125f9d6ff96c90f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="project-files"></a>Proje Dosyaları
Visual C++ proje dosyası .vcxproj dosya adı uzantısına sahip ve bir Visual C++ projesi oluşturmak için gerekli bilgileri içeren bir XML tabanlı bir dosyadır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek .vcxproj dosyası belirterek üretilmiş bir **Win32 konsol uygulaması** içinde **yeni proje** iletişim kutusu. Dosya bir proje işlemek için komut satırında msbuild.exe aracını kullanın ya da **yapı** komutunu [!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)]. (Gerekli kaynağı ve başlık dosyaları sağlanmadığı için bu örnek işlenemiyor.) Bir proje dosyasındaki XML öğeleri hakkında daha fazla bilgi için bkz: [proje dosyası şema başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference).  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup Label="ProjectConfigurations">  
    <ProjectConfiguration Include="Debug|Win32">  
      <Configuration>Debug</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
    <ProjectConfiguration Include="Release|Win32">  
      <Configuration>Release</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
  </ItemGroup>  
  <PropertyGroup Label="Globals">  
    <ProjectGuid>{96F21549-A7BF-4695-A1B1-B43625B91A14}</ProjectGuid>  
    <Keyword>Win32Proj</Keyword>  
    <RootNamespace>SomeProjName</RootNamespace>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Default.props" />  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="Configuration">  
    <ConfigurationType>Application</ConfigurationType>  
    <CharacterSet>Unicode</CharacterSet>  
  </PropertyGroup>  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="Configuration">  
    <ConfigurationType>Application</ConfigurationType>  
    <WholeProgramOptimization>true</WholeProgramOptimization>  
    <CharacterSet>Unicode</CharacterSet>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
  <ImportGroup Label="ExtensionSettings">  
  </ImportGroup>  
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />  
  </ImportGroup>  
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />  
  </ImportGroup>  
  <PropertyGroup Label="UserMacros" />  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
    <LinkIncremental>true</LinkIncremental>  
  </PropertyGroup>  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
    <LinkIncremental>false</LinkIncremental>  
  </PropertyGroup>  
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
    <ClCompile>  
      <PrecompiledHeader>Use</PrecompiledHeader>  
      <WarningLevel>Level3</WarningLevel>  
      <MinimalRebuild>true</MinimalRebuild>  
      <DebugInformationFormat>EditAndContinue</DebugInformationFormat>  
      <Optimization>Disabled</Optimization>  
      <BasicRuntimeChecks>EnableFastChecks</BasicRuntimeChecks>  
      <RuntimeLibrary>MultiThreadedDebugDLL</RuntimeLibrary>  
      <PreprocessorDefinitions>WIN32;_DEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>  
    </ClCompile>  
    <Link>  
      <SubSystem>Console</SubSystem>  
      <GenerateDebugInformation>true</GenerateDebugInformation>  
    </Link>  
  </ItemDefinitionGroup>  
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
    <ClCompile>  
      <WarningLevel>Level3</WarningLevel>  
      <PrecompiledHeader>Use</PrecompiledHeader>  
      <DebugInformationFormat>ProgramDatabase</DebugInformationFormat>  
      <Optimization>MaxSpeed</Optimization>  
      <RuntimeLibrary>MultiThreadedDLL</RuntimeLibrary>  
      <FunctionLevelLinking>true</FunctionLevelLinking>  
      <IntrinsicFunctions>true</IntrinsicFunctions>  
      <PreprocessorDefinitions>WIN32;NDEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>  
    </ClCompile>  
    <Link>  
      <SubSystem>Console</SubSystem>  
      <GenerateDebugInformation>true</GenerateDebugInformation>  
      <EnableCOMDATFolding>true</EnableCOMDATFolding>  
      <OptimizeReferences>true</OptimizeReferences>  
    </Link>  
  </ItemDefinitionGroup>  
  <ItemGroup>  
    <None Include="ReadMe.txt" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClInclude Include="stdafx.h" />  
    <ClInclude Include="targetver.h" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClCompile Include="SomeProjName.cpp" />  
    <ClCompile Include="stdafx.cpp">  
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">Create</PrecompiledHeader>  
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">Create</PrecompiledHeader>  
    </ClCompile>  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />  
  <ImportGroup Label="ExtensionTargets">  
  </ImportGroup>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da C++ projeleri derleme](../ide/building-cpp-projects-in-visual-studio.md)   
 [Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)