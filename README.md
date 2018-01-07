# Struts Tiles Example

*dark theme*  
![dark](https://user-images.githubusercontent.com/32627919/34645574-b4d40c00-f338-11e7-9be2-cdd3ddfc0e04.PNG)

*light theme*  
![light](https://user-images.githubusercontent.com/32627919/34645575-b7464296-f338-11e7-8812-48f28a4cd48e.PNG)

___


### used libraries:

`pom.xml`  
```xml
	<dependency>
      <groupId>org.apache.struts</groupId>
	  <artifactId>struts-tiles</artifactId>
      <version>1.3.10</version>
    </dependency>
```

### configurations:

`tiles-definitions.xml`  
```xml
	<definition name="templates" path="/pages/tiles/common-layout.jsp">
		<put name="header" value="/pages/tiles/theme-dark/header.jsp" />
		<put name="footer" value="/pages/tiles/theme-dark/footer.jsp" />
	</definition>
```

`struts-config.xml`  
```xml
	<action
		path="/User"
		type="org.apache.struts.actions.ForwardAction"
		parameter="/pages/user/user-form.jsp"/>
			
	<plug-in className="org.apache.struts.tiles.TilesPlugin" >
		<set-property property="definitions-config" value="/WEB-INF/tiles-definitions.xml"/>
	</plug-in>
```

`common-layout.jsp`  
```xml
	<tiles:insert attribute="header"/>

	<tiles:insert attribute="body"/> 

	<tiles:insert attribute="footer"/>
```

```user-form.jsp`  
```xml
	<tiles:insert definition="templates" >
		<tiles:put name="body" value="/pages/user/body/user-form-body.jsp" />
	</tiles:insert>
```

___

Links:

http://www.mkyong.com/struts/struts-tiles-framework-example/

https://getbootstrap.com/docs/4.0/