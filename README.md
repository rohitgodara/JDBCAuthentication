# JDBCAuthentication
JDBC Authentication >> https://docs.spring.io/spring-security/site/docs/current/reference/html5/#servlet-authentication-jdbc


1 The authentication Filter from Reading the Username & Password passes a UsernamePasswordAuthenticationToken to the AuthenticationManager which is implemented by ProviderManager.

2 The ProviderManager is configured to use an AuthenticationProvider of type DaoAuthenticationProvider.

3 DaoAuthenticationProvider looks up the UserDetails from the UserDetailsService.

4 DaoAuthenticationProvider then uses the PasswordEncoder to validate the password on the UserDetails returned in the previous step.

5 When authentication is successful, the Authentication that is returned is of type UsernamePasswordAuthenticationToken and has a principal that is the UserDetails returned by the configured UserDetailsService. Ultimately, the returned UsernamePasswordAuthenticationToken will be set on the SecurityContextHolder by the authentication Filter.